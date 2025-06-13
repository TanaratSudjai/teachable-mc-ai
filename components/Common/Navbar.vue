<template>
  <nav class="bg-gradient-to-r from-[#14a468] to-[#0f8c57] shadow-lg sticky top-0 z-50">
    <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto px-6 py-4">
      <a href="/" class="flex items-center space-x-3 rtl:space-x-reverse group">
        <div class="relative">
          <div class="absolute -inset-1 bg-white rounded-full opacity-25 group-hover:opacity-40 blur-sm transition-all duration-300"></div>
          <img
            src="https://png.pngtree.com/template/20200309/ourmid/pngtree-healthy-food-logo-with-plate-spoon-and-fork-line-art-image_355051.jpg"
            class="h-10 w-10 rounded-full relative z-10 transition-transform duration-300 group-hover:scale-110"
            alt="AI Scan Food Logo"
          />
        </div>
        <span class="self-center text-2xl font-bold text-white tracking-tight">
          <span class="text-white">AI</span> 
          <span class="text-yellow-200">Scan</span> 
          <span class="text-white">Food</span>
        </span>
      </a>
      
      <button
        @click="toggleMenu"
        type="button"
        class="inline-flex items-center p-2 w-10 h-10 justify-center text-white rounded-lg md:hidden hover:bg-[#0d7a4b] focus:outline-none focus:ring-2 focus:ring-white transition-all duration-200"
        aria-controls="navbar-default"
        :aria-expanded="menuOpen"
      >
        <span class="sr-only">Toggle menu</span>
        <svg
          class="w-6 h-6"
          aria-hidden="true"
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            v-if="!menuOpen"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          />
          <path
            v-else
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </button>
      
      <div :class="[menuOpen ? 'block' : 'hidden', 'w-full md:block md:w-auto transition-all duration-300 ease-in-out']" id="navbar-default">
        <ul class="font-medium flex flex-col p-4 mt-4 md:p-0 md:mt-0 md:flex-row md:space-x-1 rtl:space-x-reverse">
          <li v-for="(item, index) in navItems" :key="index">
            <a
              :href="item.href"
              :class="[isActivePage(item.href) ? 
                'bg-white/20 text-white md:bg-white/20' : 
                'text-white/80 hover:bg-white/10 md:hover:bg-white/10', 
                'block py-2 px-4 rounded-lg transition-all duration-200 md:px-3 md:py-2 md:text-sm md:font-semibold']"
            >
              <span class="flex items-center">
                <span v-html="item.icon" class="mr-2"></span>
                {{ item.text }}
              </span>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const menuOpen = ref(false);
const currentPath = ref('');

const toggleMenu = () => {
  menuOpen.value = !menuOpen.value;
};

const navItems = [
  { text: 'ข่าวสาร', href: '/', icon: '<svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20"><path d="M10.707 2.293a1 1 0 00-1.414 0l-7 7a1 1 0 001.414 1.414L4 10.414V17a1 1 0 001 1h2a1 1 0 001-1v-2a1 1 0 011-1h2a1 1 0 011 1v2a1 1 0 001 1h2a1 1 0 001-1v-6.586l.293.293a1 1 0 001.414-1.414l-7-7z"></path></svg>' },
  { text: 'เกี่ยวกับเรา', href: '/about', icon: '<svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M18 10a8 8 0 11-16 0 8 8 0 0116 0zm-7-4a1 1 0 11-2 0 1 1 0 012 0zM9 9a1 1 0 000 2v3a1 1 0 001 1h1a1 1 0 100-2v-3a1 1 0 00-1-1H9z" clip-rule="evenodd"></path></svg>' },
  { text: 'บริการ', href: '/service', icon: '<svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20"><path fill-rule="evenodd" d="M6 2a1 1 0 00-1 1v1H4a2 2 0 00-2 2v10a2 2 0 002 2h12a2 2 0 002-2V6a2 2 0 00-2-2h-1V3a1 1 0 10-2 0v1H7V3a1 1 0 00-1-1zm0 5a1 1 0 000 2h8a1 1 0 100-2H6z" clip-rule="evenodd"></path></svg>' },
  { text: 'ใช้บริการ', href: '/howtouse', icon: '<svg class="w-4 h-4" fill="currentColor" viewBox="0 0 20 20"><path d="M5 3a2 2 0 00-2 2v2a2 2 0 002 2h2a2 2 0 002-2V5a2 2 0 00-2-2H5zM5 11a2 2 0 00-2 2v2a2 2 0 002 2h2a2 2 0 002-2v-2a2 2 0 00-2-2H5zM11 5a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2V5zM14 11a1 1 0 011 1v1h1a1 1 0 110 2h-1v1a1 1 0 11-2 0v-1h-1a1 1 0 110-2h1v-1a1 1 0 011-1z"></path></svg>' },
];

const isActivePage = (href) => {
  if (typeof window !== 'undefined') {
    return window.location.pathname === href;
  }
  return false;
};

onMounted(() => {
  if (typeof window !== 'undefined') {
    currentPath.value = window.location.pathname;
  }
});
</script>

<style scoped>
/* Add subtle hover animation to nav items */
a {
  position: relative;
  overflow: hidden;
}

@media (min-width: 768px) {
  a::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 50%;
    width: 0;
    height: 2px;
    background-color: white;
    transition: width 0.3s ease, left 0.3s ease;
  }

  a:hover::after {
    width: 100%;
    left: 0;
  }
}
</style>
