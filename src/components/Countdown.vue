<template>
  <div class="px-2 py-4">
   
    <section class="flex justify-center gap-3 ">
      <template v-for="(value, name, index) in countdown" :key="index">
        <div 
          data-aos="zoom-in"
          class="text-center w-3/12">
          <p class="text-3xl font-medium text-amber-500 mb-2">{{ value }}</p>
          <p class="text-gray-100 text-sm font-medium">{{ name }}</p>
        </div>
      </template>
    </section>
  </div>
</template>

<script setup>

import { ref } from 'vue'

const countdown = ref(null)

// Handler for countdown
const createTimer = (target, container, cb) => {
   
   // Container => variable for return result
   // cb => callback if countdown finish

   const now = new Date().getTime()
   const distance = target - now
   if ( distance > 0 ) {
     const gun = Math.floor(distance / (1000 * 60 * 60 * 24));
     const saat = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
     const dakika = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
     const saniye = Math.floor((distance % (1000 * 60)) / 1000);
      
     container.value = { gun, saat, dakika, saniye }
     //alert(JSON.stringify(container))
      
     if (gun === 0 && saat === 0 && dakika === 0 && saniye === 0 ) cb()
   } else {
     container.value = { gun: 0, saat: 0, dakika: 0, saniye: 0 }
   } 
}

const timer = setInterval(() => {
  createTimer(new Date('2025-08-04 16:00').getTime(), countdown, () => {
    clearInterval(timer)
  })
}, 1000)



</script>
