<template>
  <div>
    <section class="text-gray py-20 relative">
      <!-- Lapisan hitam transparan tipis -->
      <div class="container mx-auto px-4 relative z-10">
        <div class="max-w-2xl">
          <!-- Card untuk teks, pastikan teks dan background tidak terkena mode gelap -->
          <div class="bg-white bg-opacity-60 p-6 rounded-lg shadow-lg">
            <h1 class="text-4xl font-bold mb-4 text-black">Jasa Sedot WC Profesional</h1>
            <p class="text-xl mb-8 text-black">Layanan sedot WC terpercaya, berpengalaman, dan bergaransi</p>
            <p class="text-xl mb-8 font-extrabold text-black">Sedot WC ? Di Go Clean Aja, Dijamin Murah Bergaransi</p>
            <a
              href="https://api.whatsapp.com/send?phone=6287777843845&text=Asslamualaikum%20Saya%20Mau%20Pesan%20Layanan%20Sedot%20Wc%20Nya%20"
              class="bg-gray-700 text-white px-6 py-3 rounded-lg font-semibold hover:bg-gray-300 hover:text-black inline-flex items-center"
            >
              <Icon icon="ic:baseline-whatsapp" width="24" height="24" class="mr-2" />
              Hubungi Kami Sekarang
            </a>
          </div>
        </div>
      </div>
    </section>

    <!-- Scrolling Slogan Section -->
    <div class="bg-gray-100 dark:bg-gray-900 text-gray-800 dark:text-gray-100 transition-colors duration-300 py-4 overflow-hidden">
      <div class="container mx-auto px-4">
        <!-- Left to Right Animation -->
        <div class="relative overflow-hidden mb-2">
          <div class="flex whitespace-nowrap animate-scroll-left">
            <div v-for="(slogan, index) in leftToRightSlogans" :key="index" class="mx-2 px-4 py-2 bg-white/50 dark:bg-gray-800/50 rounded-lg shadow-md">
              <span class="text-lg text-gray-700 dark:text-gray-300">{{ slogan }}</span>
            </div>
          </div>
        </div>

        <!-- Right to Left Animation -->
        <div class="relative overflow-hidden">
          <div class="flex whitespace-nowrap animate-scroll-right">
            <div v-for="(slogan, index) in rightToLeftSlogans" :key="index" class="mx-2 px-4 py-2 bg-white/50 dark:bg-gray-800/50 rounded-lg shadow-md">
              <span class="text-lg text-gray-700 dark:text-gray-300">{{ slogan }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { Icon } from '@iconify/vue';

const leftToRightSlogans = ['Ahli Sedot WC Termurah', 'Bersih, Cepat, dan Profesional', 'Layanan 24 Jam Siap Membantu'];
const rightToLeftSlogans = ['Garansi Kepuasan 100%', 'Teknisi Berpengalaman', 'Harga Transparan Tanpa Biaya Tersembunyi'];
</script>

<style scoped>
@keyframes scrollLeft {
  from {
    transform: translateX(100%);
  }
  to {
    transform: translateX(-100%);
  }
}

@keyframes scrollRight {
  from {
    transform: translateX(-100%);
  }
  to {
    transform: translateX(100%);
  }
}

.animate-scroll-left {
  animation: scrollLeft 15s linear infinite;
}

.animate-scroll-right {
  animation: scrollRight 15s linear infinite;
}

.bg-primary {
  background-color: #4caf50; /* Custom primary color */
}

/* Menambahkan background image untuk tampilan mobile */
@media (max-width: 640px) {
  section {
    background-image: url('/banner.jpg'); /* Menyebutkan path relatif untuk file yang ada di folder public */
    background-size: cover;
    background-position: center;
  }
}

/* Card untuk teks dengan background tipis */
.bg-white {
  background-color: rgba(255, 255, 255, 0.6); /* Menggunakan rgba untuk memberikan transparansi */
}
</style>
