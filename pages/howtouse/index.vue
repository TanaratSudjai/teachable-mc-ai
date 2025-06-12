<template>
  <div class="bg-white min-h-screen text-gray-800">
    <div class="max-w-3xl mx-auto py-16 px-4">
      <h1 class="text-3xl font-bold text-[#14a468] mb-6 text-center">
        📱 วิธีใช้บริการ
      </h1>

      <ol class="list-decimal list-inside space-y-3 text-gray-700">
        <li>ลงชื่อเข้าใช้เว็บไซต์หรือแอป</li>
        <li>คลิก "สแกนภาพอาหาร" ดึงจากกล้องหรืออัปโหลด</li>
        <li>รอ AI วิเคราะห์ และดูแคลอรี่/โภชนาการในทันที</li>
        <li>ตรวจสอบและปรับแก้หากต้องการ</li>
        <li>บันทึกผลลงในระบบเพื่อดูย้อนหลังได้</li>
      </ol>

      <img
        src="https://spikeapi.com/wp-content/uploads/2024/07/nutrition_hero-1024x625.jpg"
        class="mt-8 mx-auto rounded-lg shadow"
      />
    </div>

    <div class="max-w-3xl mx-auto px-4 pb-16 text-center">
      <h2 class="text-xl font-semibold text-[#14a468] mb-4">
        ทดลองสแกนด้วยกล้อง
      </h2>
      <button
        class="bg-[#14a468] hover:bg-[#108c5d] text-white px-6 py-2 rounded shadow mb-4"
        @click="init"
      >
        ▶️ เริ่มต้นการสแกน
      </button>
      <div id="webcam-container" class="flex justify-center mb-4"></div>
      
      <!-- ส่วนแสดงผลการวิเคราะห์ -->
      <div v-if="currentFood" class="bg-white rounded-lg shadow-lg p-6 mb-6 max-w-md mx-auto">
        <div class="flex items-center justify-between mb-4">
          <h3 class="text-xl font-bold text-[#14a468]">ผลการวิเคราะห์</h3>
          <div class="bg-[#14a468] text-white text-xs px-2 py-1 rounded-full">{{ (currentFood.confidence * 100).toFixed(0) }}% แม่นยำ</div>
        </div>
        
        <div class="flex items-center mb-4">
          <div class="bg-gray-100 p-2 rounded-full mr-4">
            <span class="text-2xl">{{ getFoodEmoji(currentFood.name) }}</span>
          </div>
          <div>
            <h4 class="font-bold text-lg">{{ currentFood.name }}</h4>
            <p class="text-[#14a468] font-semibold">{{ getFoodCalories(currentFood.name) }} แคลอรี่</p>
          </div>
        </div>
        
        <div class="bg-gray-50 p-3 rounded-md text-sm">
          <div class="flex justify-between mb-1">
            <span>โปรตีน</span>
            <span class="font-semibold">{{ getFoodProtein(currentFood.name) }}g</span>
          </div>
          <div class="flex justify-between mb-1">
            <span>คาร์โบไฮเดรต</span>
            <span class="font-semibold">{{ getFoodCarbs(currentFood.name) }}g</span>
          </div>
          <div class="flex justify-between">
            <span>ไขมัน</span>
            <span class="font-semibold">{{ getFoodFat(currentFood.name) }}g</span>
          </div>
        </div>
      </div>
      
      <!-- ส่วนแสดงเมื่อไม่พบอาหาร -->
      <div v-else-if="scanActive" class="bg-white rounded-lg shadow-lg p-6 mb-6 max-w-md mx-auto">
        <div class="flex items-center mb-4">
          <div class="bg-gray-100 p-2 rounded-full mr-4">
            <span class="text-2xl">❓</span>
          </div>
          <div>
            <h4 class="font-bold text-lg">ไม่สามารถระบุอาหารได้</h4>
            <p class="text-gray-600">กรุณาลองภาพอื่น หรือปรับตำแหน่งอาหาร</p>
          </div>
        </div>
        
        <div class="bg-yellow-50 p-3 rounded-md text-sm border border-yellow-100">
          <p>ระบบสามารถตรวจจับอาหารได้เฉพาะที่ได้รับการฝึกสอนเท่านั้น</p>
          <p class="mt-1 text-xs text-gray-500">ตัวอย่างอาหารที่รองรับ: ข้าวไข่เจียว, ข้าวขาหมู, ต้มยำกุ้ง, ฯลฯ</p>
        </div>
      </div>
      
      <!-- ส่วนแสดงผลการทำนายทั้งหมด -->
      <div id="label-container" class="space-y-1 text-gray-700 text-sm"></div>
    </div>
  </div>
</template>

<script setup>
import { onBeforeUnmount, ref } from "vue";
import * as tmImage from "@teachablemachine/image";

const URL = "https://teachablemachine.withgoogle.com/models/EB2h8Fb06/";
let model, webcam, labelContainer, maxPredictions;
const currentFood = ref(null);
const scanActive = ref(false);

// ค่าความมั่นใจขั้นต่ำที่ยอมรับได้ (0.9 = 90%)
const CONFIDENCE_THRESHOLD = 0.8;

// ฐานข้อมูลอาหารและแคลอรี่
const foodDatabase = {
  "ข้าวไข่เจียว": { calories: 450, protein: 15, carbs: 60, fat: 12, emoji: "🍳" },
  "ข้าวขาหมู": { calories: 650, protein: 28, carbs: 70, fat: 25, emoji: "🍖" },
  "ไข่ต้ม": { calories: 70, protein: 6, carbs: 0, fat: 5, emoji: "🥚" },
  "ข้าวเหนียวมะม่วง": { calories: 350, protein: 5, carbs: 65, fat: 8, emoji: "🥭" },
  "ต้มยำกุ้ง": { calories: 280, protein: 18, carbs: 10, fat: 12, emoji: "🍲" },
  "น่องไก่ทอด": { calories: 320, protein: 22, carbs: 12, fat: 18, emoji: "🍗" },
  "ผัดซีอิ๊ว": { calories: 520, protein: 15, carbs: 75, fat: 16, emoji: "🍜" },
  "แพนเค้ก": { calories: 380, protein: 8, carbs: 55, fat: 14, emoji: "🥞" },
    "เฟรนช์ฟรายส์": { calories: 310, protein: 4, carbs: 40, fat: 15, emoji: "🍟" },
  "แอปเปิ้ล": { calories: 95, protein: 0.5, carbs: 25, fat: 0.3, emoji: "🍎" }
};

// ฟังก์ชันสำหรับดึงข้อมูลอาหาร
function getFoodCalories(foodName) {
  return foodDatabase[foodName]?.calories || 0;
}

function getFoodProtein(foodName) {
  return foodDatabase[foodName]?.protein || 0;
}

function getFoodCarbs(foodName) {
  return foodDatabase[foodName]?.carbs || 0;
}

function getFoodFat(foodName) {
  return foodDatabase[foodName]?.fat || 0;
}

function getFoodEmoji(foodName) {
  return foodDatabase[foodName]?.emoji || "🍽️";
}

async function init() {
  const modelURL = URL + "model.json";
  const metadataURL = URL + "metadata.json";

  // โหลดโมเดล
  model = await tmImage.load(modelURL, metadataURL);
  maxPredictions = model.getTotalClasses();

  // จัดการกล้อง
  const flip = true;
  webcam = new tmImage.Webcam(400, 400, flip);
  await webcam.setup();
  await webcam.play();
  window.requestAnimationFrame(loop);

  // แสดงวิดีโอ
  document.getElementById("webcam-container").appendChild(webcam.canvas);

  // จัดการ label container
  labelContainer = document.getElementById("label-container");
  for (let i = 0; i < maxPredictions; i++) {
    labelContainer.appendChild(document.createElement("div"));
  }
  
  // เริ่มสแกน
  scanActive.value = true;
}

async function loop() {
  webcam.update();
  await predict();
  window.requestAnimationFrame(loop);
}

async function predict() {
  const prediction = await model.predict(webcam.canvas);
  
  // หาอาหารที่มีความแม่นยำสูงที่สุด
  let highestPrediction = { confidence: 0 };
  
  for (let i = 0; i < maxPredictions; i++) {
    const classPrediction =
      prediction[i].className + ": " + prediction[i].probability.toFixed(2);
    labelContainer.childNodes[i].innerHTML = classPrediction;
    
    // เก็บค่าความมั่นใจสูงสุด
    if (prediction[i].probability > highestPrediction.confidence) {
      highestPrediction = {
        name: prediction[i].className,
        confidence: prediction[i].probability
      };
    }
  }
  
  // ตรวจสอบว่าค่าความมั่นใจสูงกว่าเกณฑ์หรือไม่
  if (highestPrediction.confidence >= CONFIDENCE_THRESHOLD) {
    currentFood.value = highestPrediction;
  } else {
    // ถ้าความมั่นใจต่ำกว่าเกณฑ์ ให้แสดงว่าไม่สามารถระบุได้
    currentFood.value = null;
  }
}

// ทำความสะอาดเมื่อออกจากหน้า
onBeforeUnmount(() => {
  if (webcam) {
    webcam.stop();
  }
  scanActive.value = false;
});
</script>

<style scoped>
#webcam-container canvas {
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

/* เพิ่มเอฟเฟคเมื่อมีการแสดงผลอาหาร */
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

div[v-if="currentFood"], div[v-else-if="scanActive"] {
  animation: fadeIn 0.3s ease-out;
}
</style>