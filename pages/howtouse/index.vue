<template>
  <div class="bg-gradient-to-b from-white to-gray-50">
    <!-- Hero Section with Animated Background -->
    <div
      class="relative overflow-hidden bg-gradient-to-r from-[#14a468] to-[#0f8c57] text-white"
    >
      <!-- Animated Circles Background -->
      <div class="absolute inset-0 overflow-hidden opacity-20">
        <div
          class="absolute -top-40 -left-40 w-80 h-80 bg-white rounded-full opacity-20 animate-float-slow"
        ></div>
        <div
          class="absolute top-20 right-10 w-60 h-60 bg-white rounded-full opacity-10 animate-float-medium"
        ></div>
        <div
          class="absolute bottom-10 left-20 w-40 h-40 bg-white rounded-full opacity-15 animate-float-fast"
        ></div>
      </div>

      <!-- Hero Content -->
      <div class="max-w-4xl mx-auto px-6 py-8 relative z-10">
        <h1 class="text-4xl md:text-5xl font-bold mb-6 text-center">
          <span class="inline-block animate-bounce-short">📱</span>
          วิธีใช้บริการสแกนอาหาร
        </h1>

        <p class="text-xl text-center max-w-2xl mx-auto mb-8 text-white/90">
          ค้นพบแคลอรี่และคุณค่าทางโภชนาการของอาหารด้วย AI อัจฉริยะของเรา
        </p>

        <!-- Hero Image with Shadow Effect -->
        <div
          class="relative mx-auto max-w-2xl rounded-xl overflow-hidden shadow-2xl transform hover:scale-[1.02] transition-transform duration-500"
        >
          <img
            src="https://spikeapi.com/wp-content/uploads/2024/07/nutrition_hero-1024x625.jpg"
            class="w-full h-auto"
            alt="AI Food Scanning"
          />
          <div
            class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-60"
          ></div>
        </div>
      </div>
    </div>
  </div>

  <!-- Steps Section -->
  <div class="max-w-4xl mx-auto px-6 py-8">
    <h2 class="text-3xl font-bold text-[#14a468] mb-10 text-center">
      <span class="relative inline-block">
        ขั้นตอนการใช้งาน
        <span
          class="absolute -bottom-2 left-0 w-full h-1 bg-gradient-to-r from-[#14a468] to-[#0f8c57] rounded-full"
        ></span>
      </span>
    </h2>

    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16">
      <!-- Step 1 -->
      <div
        class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1"
      >
        <div
          class="flex items-center justify-center w-12 h-12 rounded-full bg-[#14a468] text-white font-bold mb-4 mx-auto"
        >
          1
        </div>
        <h3 class="text-lg font-semibold text-center mb-3">ลงชื่อเข้าใช้</h3>
        <p class="text-gray-600 text-center">
          ลงชื่อเข้าใช้เว็บไซต์หรือแอปของเราเพื่อเข้าถึงบริการสแกนอาหาร
        </p>
      </div>

      <!-- Step 2 -->
      <div
        class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1"
      >
        <div
          class="flex items-center justify-center w-12 h-12 rounded-full bg-[#14a468] text-white font-bold mb-4 mx-auto"
        >
          2
        </div>
        <h3 class="text-lg font-semibold text-center mb-3">สแกนภาพอาหาร</h3>
        <p class="text-gray-600 text-center">
          ใช้กล้องถ่ายภาพหรืออัปโหลดรูปภาพอาหารที่ต้องการวิเคราะห์
        </p>
      </div>

      <!-- Step 3 -->
      <div
        class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1"
      >
        <div
          class="flex items-center justify-center w-12 h-12 rounded-full bg-[#14a468] text-white font-bold mb-4 mx-auto"
        >
          3
        </div>
        <h3 class="text-lg font-semibold text-center mb-3">รับผลวิเคราะห์</h3>
        <p class="text-gray-600 text-center">
          รอ AI วิเคราะห์และแสดงข้อมูลแคลอรี่และโภชนาการในทันที
        </p>
      </div>
    </div>
  </div>

  <div class="max-w-4xl mx-auto px-6 pb-16">
    <!-- Scanning Section Header -->
    <div class="text-center mb-4">
      <h2 class="text-2xl md:text-3xl font-bold text-[#14a468] mb-3">
        <span class="relative inline-block">
          🔍 ทดลองสแกนอาหารด้วย AI
          <span
            class="absolute -bottom-2 left-0 w-full h-1 bg-gradient-to-r from-[#14a468] to-[#0f8c57] rounded-full"
          ></span>
        </span>
      </h2>
      <p class="text-gray-600 max-w-2xl mx-auto">
        ใช้กล้องเว็บแคมหรืออัปโหลดภาพอาหารเพื่อให้ AI
        วิเคราะห์แคลอรี่และคุณค่าทางโภชนาการ
      </p>
    </div>
  </div>

  <!-- Scanning Options Card -->
  <div class="bg-white rounded-xl shadow-lg p-6 mb-6 max-w-md mx-auto">
    <h3 class="text-lg font-semibold text-[#14a468] mb-6 text-center">
      เลือกวิธีการสแกน 
    </h3>

    <!-- ตัวเลือกการสแกน -->
    <div class="flex flex-col gap-4 mb-6 items-center">
      <!-- ปุ่มสแกนด้วยกล้อง -->
      <button
        class="w-full bg-[#14a468] hover:bg-[#108c5d] text-white py-4 rounded-lg shadow-md hover:shadow-lg transition-all duration-300 flex items-center justify-center gap-2 font-medium"
        @click="init"
        v-if="!scanActive"
      >
        <span class="text-xl">📷</span> เริ่มต้นสแกนด้วยกล้อง
      </button>
      <button
        class="w-full bg-red-500 hover:bg-red-600 text-white py-4 rounded-lg shadow-md hover:shadow-lg transition-all duration-300 flex items-center justify-center gap-2 font-medium"
        @click="stopWebcam"
        v-else
      >
        <span class="text-xl">⏹️</span> หยุดสแกน
      </button>

      <!-- ปุ่มอัปโหลดรูปภาพ -->
      <label
        class="w-full cursor-pointer bg-blue-500 hover:bg-blue-600 text-white py-4 rounded-lg shadow-md hover:shadow-lg transition-all duration-300 flex items-center justify-center gap-2 font-medium"
      >
        <span class="text-xl">🍱</span> อัปโหลดรูปภาพ
        <input
          type="file"
          class="hidden"
          accept="image/*"
          @change="handleImageUpload"
        />
      </label>
    </div>

    <!-- แสดงสถานะการโหลด -->
    <div v-if="isLoading" class="mb-8 text-center">
      <div class="relative inline-flex">
        <div
          class="absolute inset-0 rounded-full bg-gradient-to-r from-[#14a468] to-[#0f8c57] opacity-30 blur-md animate-pulse"
        ></div>
        <div
          class="relative inline-block animate-spin rounded-full h-16 w-16 border-t-3 border-b-3 border-[#14a468]"
        ></div>
      </div>
      <p class="text-gray-600 mt-4 font-medium animate-pulse">
        กำลังเตรียมระบบ AI...
      </p>
    </div>

    <!-- แสดงกล้องเว็บแคม -->
    <div v-if="scanActive" class="mb-6 max-w-md mx-auto">
      <div class="flex justify-center mb-2 relative">
        <!-- เพิ่มกรอบตกแต่งรอบกล้อง -->
        <div
          class="absolute -inset-1 bg-gradient-to-r from-[#14a468] to-[#14a468] rounded-lg opacity-70 blur-sm"
        ></div>
        <div id="webcam-container" class="relative z-10 w-full max-w-md rounded-lg overflow-hidden"></div>
        
        <!-- ปุ่มสลับกล้อง -->
        <button 
          @click="switchCamera"
          class="absolute bottom-3 right-3 z-20 bg-white/80 hover:bg-white text-gray-800 p-2 rounded-full shadow-lg backdrop-blur-sm transition-all duration-300"
          title="สลับกล้องหน้า/หลัง"
        >
          <span class="text-xl">{{ isFrontCamera ? '📱' : '📷' }}</span>
        </button>
      </div>
      <div class="flex justify-between items-center mt-2">
        <p class="text-sm text-gray-500 italic">
          กำลังสแกนอาหารด้วย AI...
        </p>
        <p class="text-xs text-gray-500">
          กำลังใช้: {{ isFrontCamera ? 'กล้องหน้า' : 'กล้องหลัง' }}
        </p>
      </div>
    </div>

    <!-- แสดงรูปภาพที่อัปโหลด -->
    <div v-if="uploadedImage" class="mb-6 max-w-md mx-auto">
      <div class="relative w-full">
        <img
          :src="uploadedImage"
          class="w-full rounded-lg shadow-md"
          ref="uploadedImageElement"
        />
        <button
          @click="clearImage"
          class="absolute top-2 right-2 bg-red-500 hover:bg-red-600 text-white rounded-full w-8 h-8 flex items-center justify-center shadow-md"
          title="ลบรูปภาพ"
        >
          ✕
        </button>
      </div>
    </div>

    <!-- ส่วนแสดงผลการวิเคราะห์ -->
    <div
      v-if="!currentFood || currentFood.confidence < 0.8"
      class="bg-white rounded-lg shadow-lg mb-6 max-w-md mx-auto overflow-hidden"
    >
      <!-- ส่วนหัวแสดงความแม่นยำ
      <div class="bg-[#14a468] text-white p-4">
        <div class="flex items-center justify-between">
          <h3 class="text-xl font-bold">ไม่สามารถระบุอาหารได้</h3>
        </div>
      </div>

      ส่วนแสดงข้อมูล
      <div class="p-4">
        <div class="flex items-center mb-4">
          <div
            class="bg-gray-100 p-3 rounded-full mr-4 flex items-center justify-center"
          >
            <span class="text-3xl">❓</span>
          </div>
          <div>
            <p class="text-gray-600">กรุณาลองภาพอื่น หรือปรับตำแหน่งอาหาร</p>
          </div>
        </div>
      </div>  -->

      
      <!-- <div class="bg-yellow-50 p-4 border-t border-yellow-100">
        <p class="text-sm text-gray-700 mb-2">
          ระบบสามารถตรวจจับอาหารได้เฉพาะที่ได้รับการฝึกสอนเท่านั้น
        </p>
        <p class="text-sm text-gray-700">
          ตัวอย่างอาหารที่รองรับ:
          <span class="font-medium"
            >ข้าวไข่เจียว, ข้าวหมู, ส้มตำ, ผัดกะเพรา, ฯลฯ</span
          >
        </p>
      </div> -->
    </div>

    <!-- ส่วนแสดงผลการวิเคราะห์เมื่อพบอาหาร -->
    <div
      v-if="currentFood && currentFood.confidence >= 0.8"
      class="bg-white rounded-lg shadow-lg mb-6 max-w-md mx-auto overflow-hidden"
    >
      <!-- ส่วนหัวแสดงชื่ออาหาร -->
      <div class="bg-[#14a468] text-white p-4">
        <div class="flex items-center justify-between">
          <h3 class="text-xl font-bold">{{ currentFood.name }}</h3>
          <div
            class="bg-white text-[#14a468] text-xs px-2 py-1 rounded-full font-bold"
          >
            {{ (currentFood.confidence * 100).toFixed(0) }}%
          </div>
        </div>
      </div>

      <!-- ส่วนแสดงข้อมูลโภชนาการ -->
      <div class="p-4">
        <div class="flex items-center mb-4">
          <div
            class="bg-gray-100 p-3 rounded-full mr-4 flex items-center justify-center"
          >
            <span class="text-3xl">{{ getFoodEmoji(currentFood.name) }}</span>
          </div>
          <div>
            <p class="text-gray-700 font-medium">
              ประมาณ
              <span class="text-[#14a468] font-bold text-xl">{{
                getFoodCalories(currentFood.name)
              }}</span>
              แคลอรี่
            </p>
          </div>
        </div>

        <!-- ข้อมูลโภชนาการโดยละเอียด -->
        <div class="mt-4 grid grid-cols-3 gap-2 text-center">
          <div class="bg-gray-50 p-3 rounded-lg">
            <div class="text-xs text-gray-500">โปรตีน</div>
            <div class="font-bold text-gray-800 mt-1">
              {{ getFoodProtein(currentFood.name) }}g
            </div>
          </div>
          <div class="bg-gray-50 p-3 rounded-lg">
            <div class="text-xs text-gray-500">คาร์บ</div>
            <div class="font-bold text-gray-800 mt-1">
              {{ getFoodCarbs(currentFood.name) }}g
            </div>
          </div>
          <div class="bg-gray-50 p-3 rounded-lg">
            <div class="text-xs text-gray-500">ไขมัน</div>
            <div class="font-bold text-gray-800 mt-1">
              {{ getFoodFat(currentFood.name) }}g
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- ส่วนแสดงเมื่อไม่พบอาหาร -->
    <div v-if="(scanActive || uploadedImage) && (!currentFood || currentFood.confidence < 0.8)"
      class="bg-white rounded-lg shadow-lg p-6 mb-6 max-w-md mx-auto"
    >
        <div class="flex items-center mb-4">
          <div class="bg-gray-100 p-2 rounded-full mr-4">
            <span class="text-2xl">❓</span>
          </div>
          <div>
            <h4 class="font-bold text-lg">ไม่สามารถระบุอาหารได้</h4>
            <p class="text-gray-600">กรุณาลองภาพอื่น หรือปรับตำแหน่งอาหาร</p>
          </div>
        </div>

        <div
          class="bg-yellow-50 p-3 rounded-md text-sm border border-yellow-100"
        >
          <p>ระบบสามารถตรวจจับอาหารได้เฉพาะที่ได้รับการฝึกสอนเท่านั้น</p>
          <p class="mt-1 text-xs text-gray-500">
            ตัวอย่างอาหารที่รองรับ: ข้าวไข่เจียว, ข้าวขาหมู, ต้มยำกุ้ง, ฯลฯ
          </p>
        </div>
      </div>

    <!-- ส่วนแสดงรายการอาหารที่รองรับ -->
    <div class="mt-10 bg-gray-50 p-4 rounded-lg max-w-md mx-auto">
      <h3 class="font-semibold text-[#14a468] mb-2">
        อาหารที่รองรับการตรวจจับ
      </h3>
      <div class="grid grid-cols-2 gap-2 text-sm">
        <div
          v-for="(food, name) in foodDatabase"
          :key="name"
          class="flex items-center"
        >
          <span class="mr-1">{{ food.emoji }}</span>
          <span>{{ name }}</span>
        </div>
      </div>
    </div>

    <!-- ส่วนแสดงผลการทำนายทั้งหมด (แสดงเฉพาะเมื่อใช้กล้อง) -->
    <div
      v-if="scanActive && !uploadedImage"
      id="label-container"
      class="space-y-1 text-gray-700 text-sm mt-4 max-w-md mx-auto bg-gray-50 p-3 rounded-md"
    ></div>
  </div>
</template>

<script setup>
import { onBeforeUnmount, ref } from "vue";
import * as tmImage from "@teachablemachine/image";

const MODEL_URL = "https://teachablemachine.withgoogle.com/models/EB2h8Fb06/";
let model, webcam, labelContainer, maxPredictions;
const currentFood = ref(null);
const scanActive = ref(false);
const isLoading = ref(false);
const uploadedImage = ref(null);
const uploadedImageElement = ref(null);
const isFrontCamera = ref(true); // ตัวแปรเก็บสถานะว่าใช้กล้องหน้าหรือกล้องหลัง

// ค่าความมั่นใจขั้นต่ำที่ยอมรับได้ (0.8 = 80%)
const CONFIDENCE_THRESHOLD = 0.8;

// ฐานข้อมูลอาหารและแคลอรี่
const foodDatabase = {
  ข้าวไข่เจียว: { calories: 450, protein: 15, carbs: 60, fat: 12, emoji: "🍳" },
  ข้าวขาหมู: { calories: 650, protein: 28, carbs: 70, fat: 25, emoji: "🍖" },
  ไข่ต้ม: { calories: 70, protein: 6, carbs: 0, fat: 5, emoji: "🥚" },
  ข้าวเหนียวมะม่วง: {
    calories: 350,
    protein: 5,
    carbs: 65,
    fat: 8,
    emoji: "🥭",
  },
  ต้มยำกุ้ง: { calories: 280, protein: 18, carbs: 10, fat: 12, emoji: "🍲" },
  น่องไก่ทอด: { calories: 320, protein: 22, carbs: 12, fat: 18, emoji: "🍗" },
  ผัดซีอิ๊ว: { calories: 520, protein: 15, carbs: 75, fat: 16, emoji: "🍜" },
  แพนเค้ก: { calories: 380, protein: 8, carbs: 55, fat: 14, emoji: "🥞" },
  เฟรนช์ฟรายส์: { calories: 310, protein: 4, carbs: 40, fat: 15, emoji: "🍟" },
  แอปเปิ้ล: { calories: 95, protein: 0.5, carbs: 25, fat: 0.3, emoji: "🍎" },
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

// ฟังก์ชันสำหรับโหลดโมเดล
async function loadModel() {
  isLoading.value = true;
  try {
    const modelURL = MODEL_URL + "model.json";
    const metadataURL = MODEL_URL + "metadata.json";
    model = await tmImage.load(modelURL, metadataURL);
    maxPredictions = model.getTotalClasses();

    // จัดการ label container
    labelContainer = document.getElementById("label-container");
    if (labelContainer) {
      labelContainer.innerHTML = "";
      for (let i = 0; i < maxPredictions; i++) {
        labelContainer.appendChild(document.createElement("div"));
      }
    }
    return true;
  } catch (error) {
    console.error("Error loading model:", error);
    return false;
  } finally {
    isLoading.value = false;
  }
}

// ฟังก์ชันเริ่มต้นการสแกนด้วยกล้อง
async function init() {
  currentFood.value = null;

  // โหลดโมเดล (ถ้ายังไม่ได้โหลด)
  if (!model) {
    const success = await loadModel();
    if (!success) return;
  }

  // จัดการกล้อง
  try {
    const flip = true;
    // กำหนดค่า facingMode ตามสถานะของกล้อง
    const facingMode = isFrontCamera.value ? "user" : "environment";
    
    // สร้าง constraints สำหรับกล้อง
    const constraints = {
      video: {
        width: { ideal: 400 },
        height: { ideal: 400 },
        facingMode: facingMode
      }
    };
    
    webcam = new tmImage.Webcam(400, 400, flip, constraints);
    await webcam.setup();
    await webcam.play();
    window.requestAnimationFrame(loop);

    // แสดงวิดีโอ
    const webcamContainer = document.getElementById("webcam-container");
    if (webcamContainer) {
      webcamContainer.innerHTML = "";
      webcamContainer.appendChild(webcam.canvas);
    }

    // เริ่มสแกน
    scanActive.value = true;
  } catch (error) {
    console.error("Error initializing webcam:", error);
    alert("ไม่สามารถเข้าถึงกล้องได้ กรุณาตรวจสอบการอนุญาตการใช้งานกล้อง");
  }
}

// ฟังก์ชันหยุดการสแกนด้วยกล้อง
function stopWebcam() {
  if (webcam) {
    webcam.stop();
    const webcamContainer = document.getElementById("webcam-container");
    if (webcamContainer) {
      webcamContainer.innerHTML = "";
    }
  }
  scanActive.value = false;
}

// ฟังก์ชันสลับกล้องหน้า/หลัง
async function switchCamera() {
  // สลับสถานะกล้อง
  isFrontCamera.value = !isFrontCamera.value;
  
  // ถ้ากำลังสแกนอยู่ ให้หยุดและเริ่มใหม่ด้วยกล้องที่เปลี่ยน
  if (scanActive.value) {
    // หยุดกล้องปัจจุบัน
    if (webcam) {
      webcam.stop();
    }
    
    // เริ่มกล้องใหม่
    await init();
  }
}

// ฟังก์ชันสำหรับการอัปโหลดรูปภาพ
async function handleImageUpload(event) {
  const file = event.target.files[0];
  if (!file) return;

  // หยุดการสแกนด้วยกล้องถ้ากำลังใช้งานอยู่
  if (scanActive.value) {
    stopWebcam();
  }

  // สร้าง URL สำหรับรูปภาพ
  uploadedImage.value = URL.createObjectURL(file);

  // โหลดโมเดล (ถ้ายังไม่ได้โหลด)
  if (!model) {
    const success = await loadModel();
    if (!success) return;
  }

  // รอให้รูปภาพโหลดเสร็จก่อนวิเคราะห์
  setTimeout(() => {
    if (uploadedImageElement.value) {
      predictImage(uploadedImageElement.value);
    }
  }, 300);
}

// ฟังก์ชันลบรูปภาพที่อัปโหลด
function clearImage() {
  if (uploadedImage.value) {
    URL.revokeObjectURL(uploadedImage.value);
    uploadedImage.value = null;
    currentFood.value = null;
  }
}

// ฟังก์ชันทำนายจากรูปภาพที่อัปโหลด
async function predictImage(imgElement) {
  try {
    isLoading.value = true;
    const prediction = await model.predict(imgElement);

    // หาอาหารที่มีความแม่นยำสูงที่สุด
    let highestPrediction = { confidence: 0 };

    for (let i = 0; i < maxPredictions; i++) {
      const classPrediction =
        prediction[i].className + ": " + prediction[i].probability.toFixed(2);

      if (labelContainer && labelContainer.childNodes[i]) {
        labelContainer.childNodes[i].innerHTML = classPrediction;
      }

      // เก็บค่าความมั่นใจสูงสุด
      if (prediction[i].probability > highestPrediction.confidence) {
        highestPrediction = {
          name: prediction[i].className,
          confidence: prediction[i].probability,
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
  } catch (error) {
    console.error("Error predicting image:", error);
    currentFood.value = null;
  } finally {
    isLoading.value = false;
  }
}

// ฟังก์ชันสำหรับการทำนายแบบต่อเนื่อง (สำหรับกล้อง)
async function loop() {
  if (!scanActive.value || !webcam) return;

  webcam.update();
  await predict();
  window.requestAnimationFrame(loop);
}

// ฟังก์ชันทำนายจากกล้อง
async function predict() {
  const prediction = await model.predict(webcam.canvas);

  // หาอาหารที่มีความแม่นยำสูงที่สุด
  let highestPrediction = { confidence: 0 };

  for (let i = 0; i < maxPredictions; i++) {
    const classPrediction =
      prediction[i].className + ": " + prediction[i].probability.toFixed(2);

    if (labelContainer && labelContainer.childNodes[i]) {
      labelContainer.childNodes[i].innerHTML = classPrediction;
    }

    // เก็บค่าความมั่นใจสูงสุด
    if (prediction[i].probability > highestPrediction.confidence) {
      highestPrediction = {
        name: prediction[i].className,
        confidence: prediction[i].probability,
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
  stopWebcam();
  if (uploadedImage.value) {
    URL.revokeObjectURL(uploadedImage.value);
  }
});
</script>

<style scoped>
#webcam-container canvas {
  border-radius: 8px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

/* เพิ่มเอฟเฟคเมื่อมีการแสดงผลอาหาร */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

div[v-if="currentFood"],
div[v-else-if="scanActive"] {
  animation: fadeIn 0.3s ease-out;
}

/* เพิ่มเอฟเฟคเมื่อมีการอัปโหลดรูปภาพ */
.fade-in {
  animation: fadeIn 0.3s ease-out;
}

/* สไตล์สำหรับปุ่มอัปโหลด */
input[type="file"] {
  display: none;
}
</style>
