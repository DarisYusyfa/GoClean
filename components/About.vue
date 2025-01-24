<template>
  <section class="py-16">
    <div class="container mx-auto px-4">
      <div class="max-w-3xl mx-auto">
        <h2 class="text-3xl font-bold text-center mb-8">Mengapa Memilih Kami?</h2>
        <div class="space-y-6 mt">
          <div class="flex items-start gap-4" data-aos="fade-up" data-aos-anchor-placement="bottom-bottom" data-aos-delay="200">
            <div class="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center flex-shrink-0">
              <span class="text-blue-800 text-xl">✓</span>
            </div>
            <div>
              <h3 class="text-xl font-semibold mb-2">Berpengalaman</h3>
              <p class="text-gray-600">Lebih dari 10 tahun melayani ribuan pelanggan dengan tingkat kepuasan tinggi</p>
            </div>
          </div>
          <div class="flex items-start gap-4" data-aos="fade-up" data-aos-anchor-placement="bottom-bottom" data-aos-delay="400">
            <div class="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center flex-shrink-0">
              <span class="text-blue-800 text-xl">✓</span>
            </div>
            <div>
              <h3 class="text-xl font-semibold mb-2">Profesional</h3>
              <p class="text-gray-600">Tim teknisi terlatih dan bersertifikat dengan peralatan modern</p>
            </div>
          </div>
          <div class="flex items-start gap-4" data-aos="fade-up" data-aos-anchor-placement="bottom-bottom" data-aos-delay="600">
            <div class="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center flex-shrink-0">
              <span class="text-blue-800 text-xl">✓</span>
            </div>
            <div>
              <h3 class="text-xl font-semibold mb-2">Bergaransi</h3>
              <p class="text-gray-600">Hasil kerja bergaransi dengan layanan after-service</p>
            </div>
          </div>
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
/* Tambahan styling jika diperlukan */
</style>
