<template>
  <section class="py-16">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold text-center mb-12">Layanan Kami</h2>
      <div class="grid md:grid-cols-3 sm:grid-cols-1 gap-8">
        <div class="service-card p-6 border rounded-lg shadow-lg" data-aos="zoom-in" data-aos-delay="200">
          <h3 class="text-xl font-semibold mb-4">Sedot WC Tersumbat</h3>
          <p>Mengatasi masalah WC tersumbat dengan peralatan modern</p>
        </div>
        <div class="service-card p-6 border rounded-lg shadow-lg" data-aos="zoom-in" data-aos-delay="400">
          <h3 class="text-xl font-semibold mb-4">Sedot WC Penuh</h3>
          <p>Pengurasan tangki septik dengan armada terbaik</p>
        </div>
        <div class="service-card p-6 border rounded-lg shadow-lg" data-aos="zoom-in" data-aos-delay="600">
          <h3 class="text-xl font-semibold mb-4">Perbaikan Saluran</h3>
          <p>Perbaikan dan perawatan saluran pembuangan</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { onMounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';

onMounted(() => {
  AOS.init({
    duration: 1000, // Durasi animasi 1 detik
    easing: 'ease-in-out', // Efek transisi yang halus
    once: true, // Animasi hanya berjalan sekali
  });
});
</script>

<style scoped>
.service-card {
  transition: transform 0.3s ease, filter 0.3s ease, box-shadow 0.3s ease, background-color 0.3s ease, border-color 0.3s ease;
  background-color: #fff; /* Default background color for light mode */
  border-color: #e5e7eb; /* Light border color */
  color: #1f2937; /* Text color for light mode */
}

/* Dark Mode Styles */
@media (prefers-color-scheme: dark) {
  .service-card {
    background-color: #1f2937; /* Dark background */
    border-color: #374151; /* Darker border color */
    color: #e5e7eb; /* Light text for dark mode */
  }

  .service-card:hover {
    background-color: #4b5563; /* Slightly lighter background on hover */
    border-color: #6b7280; /* Lighter border color on hover */
  }
}

.service-card:hover {
  transform: scale(1.05); /* Zoom effect */
  filter: brightness(1.1); /* Increase brightness */
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2); /* Shadow effect */
}

@media (max-width: 768px) {
  .service-card {
    margin-bottom: 16px;
  }
}
</style>
