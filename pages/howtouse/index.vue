<template>
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
import { ref, onBeforeUnmount } from "vue";

const URL = "https://teachablemachine.withgoogle.com/models/EB2h8Fb06/";
const isLoading = ref(false);
const isScanning = ref(false);

let model, webcam, labelContainer, maxPredictions;

const init = async () => {
  isLoading.value = true;

  try {
    const modelURL = URL + "model.json";
    const metadataURL = URL + "metadata.json";

    // Load the model
    model = await tmImage.load(modelURL, metadataURL);
    maxPredictions = model.getTotalClasses();

    // Setup webcam
    const flip = true;
    webcam = new tmImage.Webcam(300, 300, flip);
    await webcam.setup();
    await webcam.play();

    isScanning.value = true;
    window.requestAnimationFrame(loop);

    // Add webcam to container
    const container = document.getElementById("webcam-container");
    container.innerHTML = "";
    webcam.canvas.className = "rounded-xl shadow-lg";
    container.appendChild(webcam.canvas);

    // Setup label container
    labelContainer = document.getElementById("label-container");
    labelContainer.innerHTML = "";
    for (let i = 0; i < maxPredictions; i++) {
      const div = document.createElement("div");
      div.className = "bg-slate-50 rounded-xl p-4 border border-slate-200";
      labelContainer.appendChild(div);
    }
  } catch (error) {
    console.error("Error initializing scanner:", error);
    alert("เกิดข้อผิดพลาดในการเริ่มต้นกล้อง กรุณาลองใหม่อีกครั้ง");
  } finally {
    isLoading.value = false;
  }
};

const loop = async () => {
  if (webcam && isScanning.value) {
    webcam.update();
    await predict();
    window.requestAnimationFrame(loop);
  }
};

const predict = async () => {
  if (!model || !webcam) return;

  const prediction = await model.predict(webcam.canvas);

  for (let i = 0; i < maxPredictions; i++) {
    const probability = (prediction[i].probability * 100).toFixed(1);
    const className = prediction[i].className;

    const html = `
      <div class="flex items-center justify-between">
        <span class="font-medium text-slate-700">${className}</span>
        <div class="flex items-center space-x-2">
          <div class="w-24 bg-slate-200 rounded-full h-2">
            <div class="bg-emerald-500 h-2 rounded-full transition-all duration-300" style="width: ${probability}%"></div>
          </div>
          <span class="text-sm font-semibold text-slate-600 min-w-[3rem]">${probability}%</span>
        </div>
      </div>
    `;

    labelContainer.childNodes[i].innerHTML = html;
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

onBeforeUnmount(() => {
  if (webcam) {
    webcam.stop();
  }
});
</script>
