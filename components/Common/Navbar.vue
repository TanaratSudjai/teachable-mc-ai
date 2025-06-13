<template>
  <nav class="border-gray-200 bg-[#14a468]">
    <div
      class="max-w-screen-xl mx-auto flex flex-wrap items-center justify-between md:p-4 p-2"
    >
      <!-- Logo + Title -->
      <a href="/" class="flex items-center space-x-3 rtl:space-x-reverse">
        <img
          src="https://png.pngtree.com/template/20200309/ourmid/pngtree-healthy-food-logo-with-plate-spoon-and-fork-line-art-image_355051.jpg"
          class="h-8 rounded-full"
          alt="Logo"
        />
        <span
          class="self-center text-2xl font-semibold whitespace-nowrap text-white"
        >
          AI Scan Food
        </span>
      </a>

      <!-- Hamburger button -->
      <button
        @click="isOpen = !isOpen"
        type="button"
        class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-white rounded-lg md:hidden hover:bg-[#128257] focus:outline-none focus:ring-2 focus:ring-white"
      >
        <span class="sr-only">Open main menu</span>
        <svg v-if="!isOpen" class="w-5 h-5" fill="none" viewBox="0 0 17 14">
          <path
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M1 1h15M1 7h15M1 13h15"
          />
        </svg>
        <svg v-else class="w-5 h-5" fill="none" viewBox="0 0 24 24">
          <path
            stroke="currentColor"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </button>

      <!-- Navbar links -->
      <div :class="[isOpen ? 'block' : 'hidden', 'w-full md:block md:w-auto']">
        <ul
          class="font-medium flex flex-col mt-4 border-2 border-gray-100 rounded-sm bg-white md:bg-transparent md:flex-row md:space-x-8 md:mt-0 md:border-0"
        >
          <li>
            <a
              href="/"
              class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:p-0 md:text-white"
              aria-current="page"
              >ข่าวสาร</a
            >
          </li>
          <li>
            <a
              href="/about"
              class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:p-0 md:text-white"
              >เกี่ยวกับเรา</a
            >
          </li>
          <li>
            <a
              href="/service"
              class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:p-0 md:text-white"
              >บริการ</a
            >
          </li>
          <li>
            <a
              href="/howtouse"
              class="block py-2 px-3 text-gray-900 rounded hover:bg-gray-100 md:hover:bg-transparent md:p-0 md:text-white"
              >ใช้บริการ</a
            >
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from "vue";

const isOpen = ref(false);
</script>
