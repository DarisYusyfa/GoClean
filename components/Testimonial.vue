<template>
  <section id="testimonials" class="py-20 bg-gray-100 dark:bg-gray-900 text-gray-800 dark:text-gray-100">
    <div class="container mx-auto px-4">
      <h2 class="text-3xl font-bold text-center mb-12">Apa Kata Mereka</h2>
      <div class="overflow-x-auto">
        <div class="testimonial-wrapper flex space-x-6 gap-4">
          <div v-for="(testimonial, index) in testimonials" :key="index" class="testimonial-card bg-white dark:bg-gray-800 p-4 rounded-lg shadow-md min-w-[220px]">
            <div class="flex items-center space-x-4 mb-4">
              <!-- Menggunakan Iconify dengan benar -->
              <Icon :icon="'lets-icons:user-duotone'" width="36" height="36" class="w-10 h-10 rounded-full bg-gray-300 p-2" />
              <h3 class="font-semibold text-sm">{{ testimonial.name }}</h3>
            </div>
            <p class="text-gray-600 dark:text-gray-300 text-sm">{{ testimonial.comment }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { Icon } from '@iconify/vue';

export default {
  components: {
    Icon,
  },
  data() {
    return {
      testimonials: [
        {
          name: 'Budi Santoso',
          comment: 'Pelayanan cepat dan profesional. Sangat memuaskan!',
        },
        {
          name: 'Siti Rahayu',
          comment: 'Tim yang ramah dan hasil kerja yang bersih. Terima kasih GoClean SedotWC!',
        },
        {
          name: 'Agus Pratama',
          comment: 'Harga terjangkau dengan kualitas layanan terbaik. Recommended!',
        },
        {
          name: 'Fitriana Dewi',
          comment: 'Pokonya Puas , Bersih,Murah dan Cepat. Terima kasih GoClean SedotWC!',
        },
      ],
    };
  },
};
</script>

<style scoped>
/* Pastikan testimonial card responsif */
@media (max-width: 640px) {
  .overflow-x-auto {
    overflow-x: auto; /* Enable horizontal scroll */
  }

  .testimonial-wrapper {
    display: flex;
    animation: scrollTestimonials 30s linear infinite;
  }

  .testimonial-wrapper .testimonial-card {
    margin-right: 20px;
  }
}

/* Animasi untuk scroll testimonial */
@keyframes scrollTestimonials {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-100%);
  }
}

/* Kartu testimonial untuk dark mode */
.testimonial-card {
  transition: background-color 0.3s ease;
}

.dark .testimonial-card {
  background-color: #2d3748; /* Dark background for the card */
}
</style>
