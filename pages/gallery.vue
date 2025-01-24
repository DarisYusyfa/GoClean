<template>
  <div class="py-10">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold text-center mb-8">Gallery</h2>

      <!-- Wadah Gallery -->
      <div class="relative">
        <!-- Teks Scroll ke Kiri -->
        <div v-if="showLeftText" class="absolute inset-0 flex items-center justify-center text-white text-xl font-semibold z-10 bg-black bg-opacity-50">Scroll ke Kiri</div>

        <!-- Gallery Scrollable -->
        <div ref="gallery" class="overflow-x-auto whitespace-nowrap scroll-smooth" @scroll="handleScroll">
          <div class="inline-flex space-x-4">
            <div v-for="(photo, index) in photos" :key="index" class="flex-shrink-0 w-full sm:w-72 md:w-96 lg:w-96 xl:w-96">
              <!-- Gambar -->
              <img :src="photo.url" :alt="photo.alt" class="w-full h-72 object-cover rounded-lg shadow-lg transition duration-300 ease-in-out" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const photos = [
  {
    url: '/poto1.jpg',
    alt: 'Photo 1',
  },
  {
    url: '/poto2.jpeg',
    alt: 'Photo 2',
  },
  {
    url: '/poto3.jpeg',
    alt: 'Photo 3',
  },
  {
    url: '/poto4.jpg',
    alt: 'Photo 4',
  },
  {
    url: '/poto5.jpeg',
    alt: 'Photo 5',
  },
];

const gallery = ref(null);
const showLeftText = ref(true);

// Fungsi untuk menangani event scroll
const handleScroll = () => {
  if (gallery.value.scrollLeft > 0) {
    showLeftText.value = false; // Sembunyikan teks jika sudah digulir
  } else {
    showLeftText.value = true; // Tampilkan teks jika masih di awal
  }
};

onMounted(() => {
  handleScroll();
});
</script>

<style scoped>
/* Efek smooth scrolling */
.overflow-x-auto {
  -webkit-overflow-scrolling: touch;
}

.scroll-smooth {
  scroll-behavior: smooth;
}

/* Teks "Scroll ke Kiri" */
.absolute.inset-0 {
  display: flex;
  justify-content: center;
  align-items: center;
  pointer-events: none;
}
</style>
