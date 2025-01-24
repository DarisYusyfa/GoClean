<template>
  <section class="py-16 bg-gray-100 dark:bg-gray-900 text-gray-800 dark:text-gray-100">
    <div class="container mx-auto px-4">
      <div class="max-w-xl mx-auto">
        <h2 class="text-3xl font-bold text-center mb-8">Hubungi Kami</h2>
        <div class="rounded-lg shadow-md p-6">
          <div class="space-y-6">
            <div class="flex items-center gap-4">
              <div class="w-10 h-10 flex items-center justify-center">
                <Icon icon="mynaui:telephone" width="24" height="24" />
              </div>
              <div>
                <h3 class="font-semibold">Telepon</h3>
                <a href="tel:+6285871626208" class="text-black dark:text-gray-100"> 0812-3456-789 </a>
              </div>
            </div>
            <div class="flex items-center gap-4">
              <div class="w-10 h-10 flex items-center justify-center">
                <Icon icon="ic:baseline-whatsapp" width="24" height="24" />
              </div>
              <div>
                <h3 class="font-semibold">WhatsApp</h3>
                <a href="https://api.whatsapp.com/send?phone=6285871626208" class="text-black dark:text-gray-100"> 0858-7162-6208 </a>
              </div>
            </div>
            <div class="flex items-center gap-4">
              <div class="w-10 h-10 flex items-center justify-center">
                <Icon icon="mdi:address-marker-outline" width="24" height="24" />
              </div>
              <div>
                <h3 class="font-semibold">Alamat</h3>
                <p class="text-black dark:text-gray-100">Jl. Maleber Utara No.27, Bandung</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { Icon } from '@iconify/vue'; // Import ikon dengan benar

export default {
  components: {
    Icon, // Daftarkan komponen Icon di sini
  },
};
</script>
