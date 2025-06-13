<template>
  <div class="bg-gradient-to-b from-white to-gray-50">
    <!-- Hero Section with Animated Background -->
    <div class="relative overflow-hidden bg-gradient-to-r from-[#14a468] to-[#0f8c57] text-white">
      <!-- Animated Circles Background -->
      <div class="absolute inset-0 overflow-hidden opacity-20">
        <div class="absolute -top-40 -left-40 w-80 h-80 bg-white rounded-full opacity-20 animate-float-slow"></div>
        <div class="absolute top-20 right-10 w-60 h-60 bg-white rounded-full opacity-10 animate-float-medium"></div>
        <div class="absolute bottom-10 left-20 w-40 h-40 bg-white rounded-full opacity-15 animate-float-fast"></div>
      </div>
      
      <!-- Hero Content -->
      <div class="max-w-4xl mx-auto px-6 py-8 relative z-10">
        <h1 class="text-4xl md:text-5xl font-bold mb-6 text-center">
          <span class="inline-block animate-bounce-short">📱</span> วิธีใช้บริการสแกนอาหาร
        </h1>
        
        <p class="text-xl text-center max-w-2xl mx-auto mb-8 text-white/90">
          ค้นพบแคลอรี่และคุณค่าทางโภชนาการของอาหารด้วย AI อัจฉริยะของเรา
        </p>
        
        <!-- Hero Image with Shadow Effect -->
        <div class="relative mx-auto max-w-2xl rounded-xl overflow-hidden shadow-2xl transform hover:scale-[1.02] transition-transform duration-500">
          <img
            src="https://spikeapi.com/wp-content/uploads/2024/07/nutrition_hero-1024x625.jpg"
            class="w-full h-auto"
            alt="AI Food Scanning"
          />
          <div class="absolute inset-0 bg-gradient-to-t from-black/50 to-transparent opacity-60"></div>
        </div>
      </div>
    </div>
  </div>
    
    <!-- Steps Section -->
    <div class="max-w-4xl mx-auto px-6 py-8">
      <h2 class="text-3xl font-bold text-[#14a468] mb-10 text-center">
        <span class="relative inline-block">
          ขั้นตอนการใช้งาน
          <span class="absolute -bottom-2 left-0 w-full h-1 bg-gradient-to-r from-[#14a468] to-[#0f8c57] rounded-full"></span>
        </span>
      </h2>
      
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 mb-16">
        <!-- Step 1 -->
        <div class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1">
          <div class="flex items-center justify-center w-12 h-12 rounded-full bg-[#14a468] text-white font-bold mb-4 mx-auto">
            1
          </div>
          <h3 class="text-lg font-semibold text-center mb-3">ลงชื่อเข้าใช้</h3>
          <p class="text-gray-600 text-center">ลงชื่อเข้าใช้เว็บไซต์หรือแอปของเราเพื่อเข้าถึงบริการสแกนอาหาร</p>
        </div>
        
        <!-- Step 2 -->
        <div class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1">
          <div class="flex items-center justify-center w-12 h-12 rounded-full bg-[#14a468] text-white font-bold mb-4 mx-auto">
            2
          </div>
          <h3 class="text-lg font-semibold text-center mb-3">สแกนภาพอาหาร</h3>
          <p class="text-gray-600 text-center">ใช้กล้องถ่ายภาพหรืออัปโหลดรูปภาพอาหารที่ต้องการวิเคราะห์</p>
        </div>
        
        <!-- Step 3 -->
        <div class="bg-white p-6 rounded-xl shadow-lg hover:shadow-xl transition-shadow duration-300 transform hover:-translate-y-1">
          <div class="flex items-center justify-center w-12 h-12 rounded-full bg-[#14a468] text-white font-bold mb-4 mx-auto">
            3
          </div>
          <h3 class="text-lg font-semibold text-center mb-3">รับผลวิเคราะห์</h3>
          <p class="text-gray-600 text-center">รอ AI วิเคราะห์และแสดงข้อมูลแคลอรี่และโภชนาการในทันที</p>
        </div>
      </div>
    </div>

    <div class="max-w-4xl mx-auto px-6 pb-16">
      <!-- Scanning Section Header -->
      <div class="text-center mb-4">
        <h2 class="text-2xl md:text-3xl font-bold text-[#14a468] mb-3">
          <span class="relative inline-block">
            🔍 ทดลองสแกนอาหารด้วย AI
            <span class="absolute -bottom-2 left-0 w-full h-1 bg-gradient-to-r from-[#14a468] to-[#0f8c57] rounded-full"></span>
          </span>
        </h2>
        <p class="text-gray-600 max-w-2xl mx-auto">
          ใช้กล้องเว็บแคมหรืออัปโหลดภาพอาหารเพื่อให้ AI วิเคราะห์แคลอรี่และคุณค่าทางโภชนาการ
        </p>
      </div>
      
      <!-- Scanning Options Card -->
      <div class="bg-white rounded-xl shadow-lg p-6 mb-6 max-w-2xl mx-auto">
        <h3 class="text-lg font-semibold text-[#14a468] mb-6 text-center">เลือกวิธีการสแกน</h3>
        
        <!-- ตัวเลือกการสแกน -->
        <div class="flex flex-col sm:flex-row justify-center gap-4 mb-6 items-center">
          <button
            class="bg-gradient-to-r from-[#14a468] to-[#0f8c57] hover:from-[#108c5d] hover:to-[#0d7a4b] text-white px-6 py-3 rounded-lg shadow-md hover:shadow-lg transition-all duration-300 flex items-center justify-center gap-2 font-medium"
            @click="init"
            v-if="!scanActive"
          >
            <span class="text-xl">📷</span> เริ่มต้นสแกนด้วยกล้อง
          </button>
          <button
            class="bg-gradient-to-r from-red-500 to-red-600 hover:from-red-600 hover:to-red-700 text-white px-6 py-3 rounded-lg shadow-md hover:shadow-lg transition-all duration-300 flex items-center justify-center gap-2 font-medium"
            @click="stopWebcam"
            v-else
          >
            <span class="text-xl">⏹️</span> หยุดสแกน
          </button>
          
          <!-- ปุ่มอัปโหลดรูปภาพ -->
          <label class="cursor-pointer bg-gradient-to-r from-blue-500 to-blue-600 hover:from-blue-600 hover:to-blue-700 text-white px-6 py-3 rounded-lg shadow-md hover:shadow-lg transition-all duration-300 flex items-center justify-center gap-2 font-medium">
            <span class="text-xl">📤</span> อัปโหลดรูปภาพ
            <input type="file" class="hidden" accept="image/*" @change="handleImageUpload" />
          </label>
        </div>
      
      <!-- แสดงสถานะการโหลด -->
      <div v-if="isLoading" class="mb-8 text-center">
        <div class="relative inline-flex">
          <div class="absolute inset-0 rounded-full bg-gradient-to-r from-[#14a468] to-[#0f8c57] opacity-30 blur-md animate-pulse"></div>
          <div class="relative inline-block animate-spin rounded-full h-16 w-16 border-t-3 border-b-3 border-[#14a468]"></div>
        </div>
        <p class="text-gray-600 mt-4 font-medium animate-pulse">กำลังเตรียมระบบ AI...</p>
      </div>
      
      <!-- แสดงกล้องเว็บแคม -->
      <div v-if="scanActive" class="mb-6">
        <div id="webcam-container" class="flex justify-center mb-2 relative">
          <!-- เพิ่มกรอบตกแต่งรอบกล้อง -->
          <div class="absolute -inset-2 bg-gradient-to-r from-[#14a468] to-blue-500 rounded-lg opacity-70 blur-sm"></div>
          <div class="relative z-10"></div>
        </div>
        <p class="text-sm text-gray-500 italic">กำลังสแกนอาหารด้วย AI...</p>
      </div>
      
      <!-- แสดงรูปภาพที่อัปโหลด -->
      <div v-if="uploadedImage" class="mb-4">
        <div class="relative inline-block">
          <img :src="uploadedImage" class="max-h-[400px] rounded-lg shadow-md" ref="uploadedImageElement" />
          <button 
            @click="clearImage" 
            class="absolute top-2 right-2 bg-red-500 hover:bg-red-600 text-white rounded-full w-8 h-8 flex items-center justify-center"
            title="ลบรูปภาพ"
          >
            ✕
          </button>
        </div>
      </div>
      
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
      <div v-else-if="scanActive || uploadedImage" class="bg-white rounded-lg shadow-lg p-6 mb-6 max-w-md mx-auto">
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
      
      <!-- ส่วนแสดงรายการอาหารที่รองรับ -->
      <div class="mt-10 bg-gray-50 p-4 rounded-lg max-w-md mx-auto">
        <h3 class="font-semibold text-[#14a468] mb-2">อาหารที่รองรับการตรวจจับ</h3>
        <div class="grid grid-cols-2 gap-2 text-sm">
          <div v-for="(food, name) in foodDatabase" :key="name" class="flex items-center">
            <span class="mr-1">{{ food.emoji }}</span>
            <span>{{ name }}</span>
          </div>
        </div>
      </div>
      
      <!-- ส่วนแสดงผลการทำนายทั้งหมด (แสดงเฉพาะเมื่อใช้กล้อง) -->
      <div v-if="scanActive && !uploadedImage" id="label-container" class="space-y-1 text-gray-700 text-sm mt-4 max-w-md mx-auto bg-gray-50 p-3 rounded-md"></div>

  <div class="min-h-screen bg-gradient-to-br from-slate-50 to-slate-100">
    <!-- Header Section -->
    <div class="bg-white/80 backdrop-blur-sm border-b border-slate-200/60">
      <div class="max-w-4xl mx-auto px-6 py-8">
        <div class="text-center">
          <h1 class="text-3xl font-bold text-slate-800 mb-2">วิธีใช้บริการ</h1>
          <p class="text-slate-600 max-w-md mx-auto">
            สแกนและวิเคราะห์โภชนาการอาหารด้วย AI อัจฉริยะ
          </p>
        </div>
      </div>
    </div>

    <!-- Instructions Section -->
    <div class="max-w-4xl mx-auto px-6 py-12">
      <div class="bg-white rounded-3xl shadow-xl shadow-slate-200/50 p-8 mb-12">
        <div class="grid md:grid-cols-2 gap-12 items-center">
          <div>
            <h2 class="text-2xl font-semibold text-slate-800 mb-6">
              ขั้นตอนการใช้งาน
            </h2>
            <div class="space-y-4">
              <div class="flex items-start space-x-4 group">
                <div
                  class="flex-shrink-0 w-8 h-8 bg-emerald-100 text-emerald-600 rounded-full flex items-center justify-center font-semibold text-sm group-hover:bg-emerald-500 group-hover:text-white transition-colors duration-200"
                >
                  1
                </div>
                <div class="flex-1">
                  <p class="text-slate-700 font-medium">
                    กดปุ่ม "สแกนภาพอาหาร"
                  </p>
                  <p class="text-slate-500 text-sm mt-1">
                    เริ่มต้นการสแกนด้วยการกดปุ่มเขียว
                  </p>
                </div>
              </div>

              <div class="flex items-start space-x-4 group">
                <div
                  class="flex-shrink-0 w-8 h-8 bg-emerald-100 text-emerald-600 rounded-full flex items-center justify-center font-semibold text-sm group-hover:bg-emerald-500 group-hover:text-white transition-colors duration-200"
                >
                  2
                </div>
                <div class="flex-1">
                  <p class="text-slate-700 font-medium">
                    อนุญาตให้แอปเข้าถึงกล้อง
                  </p>
                  <p class="text-slate-500 text-sm mt-1">
                    อนุญาตการเข้าถึงกล้องเมื่อเบราว์เซอร์ถาม
                  </p>
                </div>
              </div>

              <div class="flex items-start space-x-4 group">
                <div
                  class="flex-shrink-0 w-8 h-8 bg-emerald-100 text-emerald-600 rounded-full flex items-center justify-center font-semibold text-sm group-hover:bg-emerald-500 group-hover:text-white transition-colors duration-200"
                >
                  3
                </div>
                <div class="flex-1">
                  <p class="text-slate-700 font-medium">
                    ชี้กล้องไปที่จานอาหาร
                  </p>
                  <p class="text-slate-500 text-sm mt-1">
                    จัดมุมกล้องให้เห็นอาหารชัดเจน
                  </p>
                </div>
              </div>

              <div class="flex items-start space-x-4 group">
                <div
                  class="flex-shrink-0 w-8 h-8 bg-emerald-100 text-emerald-600 rounded-full flex items-center justify-center font-semibold text-sm group-hover:bg-emerald-500 group-hover:text-white transition-colors duration-200"
                >
                  4
                </div>
                <div class="flex-1">
                  <p class="text-slate-700 font-medium">
                    รอ AI วิเคราะห์ และดูผลลัพธ์
                  </p>
                  <p class="text-slate-500 text-sm mt-1">
                    ได้ข้อมูลแคลอรี่และโภชนาการในทันที
                  </p>
                </div>
              </div>
            </div>
          </div>

          <div class="flex justify-center">
            <div class="relative">
              <img
                src="https://spikeapi.com/wp-content/uploads/2024/07/nutrition_hero-1024x625.jpg"
                alt="การสแกนอาหารด้วยแอป"
                class="rounded-2xl shadow-2xl max-w-full h-auto"
              />
              <div
                class="absolute inset-0 bg-gradient-to-t from-emerald-500/20 to-transparent rounded-2xl"
              ></div>
            </div>
          </div>
        </div>
      </div>

      <!-- Scanner Section -->
      <div class="bg-white rounded-3xl shadow-xl shadow-slate-200/50 p-8">
        <div class="text-center mb-8">
          <h2 class="text-2xl font-semibold text-slate-800 mb-4">
            ทดลองสแกนด้วยกล้อง
          </h2>
          <p class="text-slate-600 mb-6">
            กดปุ่มด้านล่างเพื่อเริ่มการสแกนและวิเคราะห์อาหาร
          </p>

          <button
            @click="init"
            :disabled="isLoading"
            class="inline-flex items-center px-8 py-4 bg-gradient-to-r from-emerald-500 to-emerald-600 hover:from-emerald-600 hover:to-emerald-700 text-white font-semibold rounded-2xl shadow-lg hover:shadow-xl transform hover:-translate-y-0.5 transition-all duration-200 disabled:opacity-50 disabled:cursor-not-allowed disabled:transform-none"
          >
            <svg
              v-if="isLoading"
              class="animate-spin -ml-1 mr-3 h-5 w-5 text-white"
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
            >
              <circle
                class="opacity-25"
                cx="12"
                cy="12"
                r="10"
                stroke="currentColor"
                stroke-width="4"
              ></circle>
              <path
                class="opacity-75"
                fill="currentColor"
                d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"
              ></path>
            </svg>
            <span v-if="!isLoading">📱 สแกนภาพอาหาร</span>
            <span v-else>กำลังโหลด...</span>
          </button>
        </div>

        <!-- Webcam Container -->
        <div class="flex justify-center mb-6">
          <div
            id="webcam-container"
            class="bg-slate-100 rounded-2xl p-4 min-h-[250px] flex items-center justify-center"
            :class="{ 'border-2 border-dashed border-slate-300': !isScanning }"
          >
            <div v-if="!isScanning" class="text-center text-slate-500">
              <div class="text-4xl mb-2">📸</div>
              <p>กดปุ่มข้างบนเพื่อเริ่มกล้อง</p>
            </div>
          </div>
        </div>

        <!-- Results Container -->
        <div id="label-container" class="space-y-3" v-show="isScanning">
          <!-- Results will be populated here -->
        </div>

        <!-- Stop Button -->
        <div class="text-center mt-6" v-if="isScanning">
          <button
            @click="stopScanning"
            class="px-6 py-2 bg-slate-200 hover:bg-slate-300 text-slate-700 font-medium rounded-xl transition-colors duration-200"
          >
            หยุดการสแกน
          </button>
        </div>
      </div>

    </div>
  </div>
</template>

<script setup>
import { onBeforeUnmount, ref } from "vue";
import * as tmImage from "@teachablemachine/image";

const MODEL_URL = "https://teachablemachine.withgoogle.com/models/EB2h8Fb06/"
let model, webcam, labelContainer, maxPredictions;
const currentFood = ref(null);
const scanActive = ref(false);
const isLoading = ref(false);
const uploadedImage = ref(null);
const uploadedImageElement = ref(null);

// ค่าความมั่นใจขั้นต่ำที่ยอมรับได้ (0.8 = 80%)
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
      labelContainer.innerHTML = '';
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
    webcam = new tmImage.Webcam(400, 400, flip);
    await webcam.setup();
    await webcam.play();
    window.requestAnimationFrame(loop);

    // แสดงวิดีโอ
    const webcamContainer = document.getElementById("webcam-container");
    if (webcamContainer) {
      webcamContainer.innerHTML = '';
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
      webcamContainer.innerHTML = '';
    }
  }
  scanActive.value = false;
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
  } catch (error) {
    console.error("Error predicting image:", error);
    currentFood.value = null;
  } finally {
    isLoading.value = false;
  }
};

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
};

const stopScanning = () => {
  isScanning.value = false;
  if (webcam) {
    webcam.stop();
  }

  const container = document.getElementById("webcam-container");
  container.innerHTML = `
    <div class="text-center text-slate-500">
      <div class="text-4xl mb-2">📸</div>
      <p>กดปุ่มข้างบนเพื่อเริ่มกล้องใหม่</p>
    </div>
  `;

  const labelContainer = document.getElementById("label-container");
  labelContainer.innerHTML = "";
};

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
  from { opacity: 0; transform: translateY(10px); }
  to { opacity: 1; transform: translateY(0); }
}

div[v-if="currentFood"], div[v-else-if="scanActive"] {
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