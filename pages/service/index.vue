<template>
  <div class="bg-white min-h-screen">
    <!-- Header -->
    <div class="max-w-5xl mx-auto px-6 py-16">
      <div class="text-center mb-16">
        <h1 class="text-4xl font-bold text-[#14a468] mb-4">🛠 บริการของเรา</h1>
        <p class="text-gray-600 text-lg max-w-2xl mx-auto">
          เทคโนโลยี AI สำหรับการวิเคราะห์โภชนาการที่แม่นยำ
        </p>
      </div>

      <!-- Services Grid -->
      <div class="grid md:grid-cols-3 gap-8 mb-16">
        <div
          class="bg-gray-50 p-8 rounded-xl text-center hover:shadow-md transition-shadow"
        >
          <div class="text-4xl mb-4">📸</div>
          <h2 class="text-xl font-semibold text-gray-800 mb-3">สแกนภาพอาหาร</h2>
          <p class="text-gray-600 leading-relaxed">
            AI วิเคราะห์เมนูจากภาพถ่าย พร้อมส่วนประกอบครบถ้วน
          </p>
        </div>

        <div
          class="bg-gray-50 p-8 rounded-xl text-center hover:shadow-md transition-shadow"
        >
          <div class="text-4xl mb-4">🔥</div>
          <h2 class="text-xl font-semibold text-gray-800 mb-3">
            วิเคราะห์โภชนาการ
          </h2>
          <p class="text-gray-600 leading-relaxed">
            ประเมินแคลอรี่ โปรตีน ไขมัน คาร์บได้แม่นยำ รองรับอาหารหลายประเภท
          </p>
        </div>

        <div
          class="bg-gray-50 p-8 rounded-xl text-center hover:shadow-md transition-shadow"
        >
          <div class="text-4xl mb-4">📊</div>
          <h2 class="text-xl font-semibold text-gray-800 mb-3">รายงานสุขภาพ</h2>
          <p class="text-gray-600 leading-relaxed">
            สถิติรายวัน-สัปดาห์ พร้อมกราฟเข้าใจง่าย
          </p>
        </div>
      </div>

      <!-- Stats -->
      <div class="grid grid-cols-2 md:grid-cols-4 gap-6 mb-16">
        <div class="text-center p-6">
          <div class="text-3xl font-bold text-[#14a468] mb-2">99%</div>
          <div class="text-gray-600">ความแม่นยำ</div>
        </div>
        <div class="text-center p-6">
          <div class="text-3xl font-bold text-[#14a468] mb-2">500+</div>
          <div class="text-gray-600">ชนิดอาหาร</div>
        </div>
        <div class="text-center p-6">
          <div class="text-3xl font-bold text-[#14a468] mb-2">&lt;3s</div>
          <div class="text-gray-600">เวลาวิเคราะห์</div>
        </div>
        <div class="text-center p-6">
          <div class="text-3xl font-bold text-[#14a468] mb-2">24/7</div>
          <div class="text-gray-600">พร้อมใช้งาน</div>
        </div>
      </div>

      <!-- Image -->
      <div class="text-center">
        <img
          src="https://www.mooglelabs.com/frontend/assests/images/slim-snap/slim-snap-banner.png"
          alt="แดชบอร์ดการวิเคราะห์โภชนาการ"
          class="w-full max-w-4xl mx-auto rounded-xl shadow-lg"
        />
      </div>

      <!-- CTA -->
      <div class="text-center mt-16">
        <div class="bg-[#14a468] text-white p-8 rounded-xl max-w-2xl mx-auto">
          <h3 class="text-2xl font-bold mb-4">เริ่มใช้งานวันนี้</h3>
          <p class="mb-6 opacity-90">ติดตามสุขภาพของคุณด้วยเทคโนโลยี AI</p>
          <button
            class="bg-white text-[#14a468] px-8 py-3 rounded-lg font-semibold hover:bg-gray-50 transition-colors"
          >
            เริ่มใช้งานฟรี
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
