<template>
  <div class="py-10">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold text-center mb-8">Gallery</h2>

      <!-- Wadah Gallery -->
      <div class="relative">
        <!-- Teks Scroll ke Kiri -->
        <div v-if="showLeftText" class="absolute inset-0 flex items-center justify-center text-white text-xl font-semibold">Scroll ke Kiri</div>

        <!-- Indikator Scroll ke Kiri -->
        <div @click="scrollLeft" class="absolute top-1/2 left-4 transform -translate-y-1/2 text-white text-3xl cursor-pointer">
          <Icon icon="fa-solid:chevron-left" />
        </div>

        <!-- Gallery Scrollable -->
        <div ref="gallery" class="overflow-x-auto" @scroll="handleScroll">
          <div class="flex space-x-4">
            <div v-for="(photo, index) in photos" :key="index" class="flex-shrink-0 w-full sm:w-72 md:w-96 lg:w-96 xl:w-96">
              <!-- Gambar -->
              <img :src="photo.url" :alt="photo.alt" class="w-full h-72 object-cover rounded-lg shadow-lg transition duration-300 ease-in-out" />
            </div>
          </div>
        </div>

        <!-- Indikator Scroll ke Kanan -->
        <div @click="scrollRight" class="absolute top-1/2 right-4 transform -translate-y-1/2 text-white text-3xl cursor-pointer">
          <Icon icon="fa-solid:chevron-right" />
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { Icon } from '@iconify/vue';
import { ref } from 'vue';

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
    url: '/poto 4.jpg',
    alt: 'Photo 4',
  },
  {
    url: '/poto5.jpeg',
    alt: 'Photo 5',
  },
];

const gallery = ref(null);
const showLeftText = ref(true); // Status untuk menampilkan teks "Scroll ke Kiri"

// Fungsi untuk menggeser ke kiri satu gambar
const scrollLeft = () => {
  const scrollAmount = gallery.value.offsetWidth; // Menggunakan lebar gallery untuk menentukan jarak geser
  gallery.value.scrollBy({ left: -scrollAmount, behavior: 'smooth' });
  showLeftText.value = false; // Sembunyikan teks saat pengguna mengklik
};

// Fungsi untuk menggeser ke kanan satu gambar
const scrollRight = () => {
  const scrollAmount = gallery.value.offsetWidth; // Menggunakan lebar gallery untuk menentukan jarak geser
  gallery.value.scrollBy({ left: scrollAmount, behavior: 'smooth' });
  showLeftText.value = false; // Sembunyikan teks saat pengguna mengklik
};

// Fungsi untuk menangani event scroll pada gallery
const handleScroll = () => {
  if (gallery.value.scrollLeft > 0) {
    showLeftText.value = false; // Sembunyikan teks jika sudah digulir
  } else {
    showLeftText.value = true; // Tampilkan teks jika masih di awal
  }
};
</script>

<style scoped>
/* Styling untuk gallery wrapper */
.gallery-wrapper {
  /* Membatasi lebar gallery pada layar mobile dan memberikan ruang pada gambar */
  overflow-x: auto;
  scroll-snap-type: x mandatory;
}

.gallery-wrapper img {
  scroll-snap-align: start;
}

/* Styling untuk indikator scroll */
.absolute {
  position: absolute;
}

.text-3xl {
  font-size: 1.875rem;
}

.text-xl {
  font-size: 1.25rem;
}

.text-white {
  color: #ffffff;
}

.cursor-pointer {
  cursor: pointer;
}

/* Memastikan teks "Scroll ke Kiri" berada di tengah */
.absolute.inset-0 {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
