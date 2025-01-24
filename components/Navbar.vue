<template>
  <nav class="bg-gray-100 dark:bg-gray-900 text-gray-800 dark:text-gray-100 shadow-md py-3 transition-colors duration-300">
    <div class="container mx-auto px-4 py-3">
      <div class="flex justify-between items-center">
        <NuxtLink to="/" class="font-bold text-gray-900 dark:text-white">
          <img src="/public/logo.png" alt="Go Clean" class="h-12 w-auto dark:hidden" />
          <img src="/public/logo.png" alt="Go Clean" class="h-12 w-auto hidden dark:block" />
        </NuxtLink>

        <!-- Hamburger Menu Button -->
        <button @click="toggleMenu" class="lg:hidden focus:outline-none">
          <svg class="w-6 h-6 text-gray-800 dark:text-white" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16m-7 6h7"></path>
          </svg>
        </button>

        <!-- Desktop Menu -->
        <div class="hidden lg:flex space-x-6">
          <NuxtLink to="/" class="hover:text-blue-600 dark:hover:text-blue-400 transition duration-300">Home</NuxtLink>
          <NuxtLink to="/services" class="hover:text-blue-600 dark:hover:text-blue-400 transition duration-300">Layanan</NuxtLink>
          <NuxtLink to="/about" class="hover:text-blue-600 dark:hover:text-blue-400 transition duration-300">Tentang</NuxtLink>
          <NuxtLink to="/contact" class="hover:text-blue-600 dark:hover:text-blue-400 transition duration-300">Kontak</NuxtLink>
        </div>
      </div>

      <!-- Mobile Menu -->
      <div v-show="isMenuOpen" class="lg:hidden mt-4 space-y-2 bg-gray-100 dark:bg-gray-800 shadow-lg rounded-lg p-4 transition-all duration-300">
        <NuxtLink to="/" class="block py-2 text-gray-800 dark:text-gray-100 border-b hover:text-blue-600 dark:hover:text-blue-400" @click="closeMenu">Home</NuxtLink>
        <NuxtLink to="/services" class="block py-2 text-gray-800 dark:text-gray-100 border-b hover:text-blue-600 dark:hover:text-blue-400" @click="closeMenu">Layanan</NuxtLink>
        <NuxtLink to="/about" class="block py-2 text-gray-800 dark:text-gray-100 border-b hover:text-blue-600 dark:hover:text-blue-400" @click="closeMenu">Tentang</NuxtLink>
        <NuxtLink to="/contact" class="block py-2 text-gray-800 dark:text-gray-100 hover:text-blue-600 dark:hover:text-blue-400" @click="closeMenu">Kontak</NuxtLink>
      </div>
    </div>
  </nav>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const isMenuOpen = ref(false);

    const toggleMenu = () => {
      isMenuOpen.value = !isMenuOpen.value;
    };

    const closeMenu = () => {
      isMenuOpen.value = false;
    };

    return {
      isMenuOpen,
      toggleMenu,
      closeMenu,
    };
  },
};
</script>
