<template>
  <div class="bg-white min-h-screen text-gray-800">
    <div class="max-w-3xl mx-auto py-16 px-4">
      <h1 class="text-3xl font-bold text-[#14a468] mb-6 text-center">
        📱 วิธีใช้บริการ
      </h1>

      <ol class="list-decimal list-inside space-y-3 text-gray-700">
        <li>ลงชื่อเข้าใช้เว็บไซต์หรือแอป</li>
        <li>คลิก “สแกนภาพอาหาร” ดึงจากกล้องหรืออัปโหลด</li>
        <li>รอ AI วิเคราะห์ และดูแคลอรี่/โภชนาการในทันที</li>
        <li>ตรวจสอบและปรับแก้หากต้องการ</li>
        <li>บันทึกผลลงในระบบเพื่อดูย้อนหลังได้</li>
      </ol>

      <img
        src="https://spikeapi.com/wp-content/uploads/2024/07/nutrition_hero-1024x625.jpg"
        alt="User scanning food with app"
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
      <div id="label-container" class="space-y-1 text-gray-700 text-sm"></div>
    </div>
  </div>
</template>

<script setup>
import { onBeforeUnmount } from "vue";
import * as tmImage from "@teachablemachine/image";

const URL = "https://teachablemachine.withgoogle.com/models/EB2h8Fb06/";
let model, webcam, labelContainer, maxPredictions;

async function init() {
  const modelURL = URL + "model.json";
  const metadataURL = URL + "metadata.json";

  model = await tmImage.load(modelURL, metadataURL);
  maxPredictions = model.getTotalClasses();

  const flip = true;
  webcam = new tmImage.Webcam(200, 200, flip);
  await webcam.setup();
  await webcam.play();
  window.requestAnimationFrame(loop);

  document.getElementById("webcam-container").innerHTML = "";
  document.getElementById("webcam-container").appendChild(webcam.canvas);

  labelContainer = document.getElementById("label-container");
  labelContainer.innerHTML = "";
  for (let i = 0; i < maxPredictions; i++) {
    labelContainer.appendChild(document.createElement("div"));
  }
}

async function loop() {
  webcam.update();
  await predict();
  window.requestAnimationFrame(loop);
}

async function predict() {
  const prediction = await model.predict(webcam.canvas);
  for (let i = 0; i < maxPredictions; i++) {
    const classPrediction =
      prediction[i].className + ": " + prediction[i].probability.toFixed(2);
    labelContainer.childNodes[i].innerHTML = classPrediction;
  }
}

onBeforeUnmount(() => {
  if (webcam) webcam.stop();
});
</script>
