<template>
  <div class="fixed bottom-4 right-4 flex items-center">
    <transition name="fade">
      <span v-if="showText" class="mr-2 text-sm bg-gray-800 text-white dark:bg-gray-200 dark:text-black px-2 py-1 rounded-md">
        {{ isDarkMode ? 'Light Mode' : 'Dark Mode' }}
      </span>
    </transition>
    <button @click="toggleDarkMode" class="w-10 h-10 flex items-center justify-center bg-gray-800 dark:bg-gray-200 text-white dark:text-black rounded-full shadow-md transition duration-300">
      {{ isDarkMode ? '☀️' : '🌙' }}
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isDarkMode: false,
      showText: false,
    };
  },
  mounted() {
    this.isDarkMode = localStorage.getItem('theme') === 'dark';
    if (this.isDarkMode) {
      document.documentElement.classList.add('dark');
    }
  },
  methods: {
    toggleDarkMode() {
      this.isDarkMode = !this.isDarkMode;
      if (this.isDarkMode) {
        document.documentElement.classList.add('dark');
        localStorage.setItem('theme', 'dark');
      } else {
        document.documentElement.classList.remove('dark');
        localStorage.setItem('theme', 'light');
      }

      this.showText = true;
      setTimeout(() => {
        this.showText = false;
      }, 6000); // Sembunyikan setelah 6 detik
    },
  },
};
</script>

<style scoped>
/* Animasi fade in dan fade out */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease-in-out;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
