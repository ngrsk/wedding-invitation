<template>
  <section class="w-full bg-couples bg-cover h-screen">
    <section class="container-section h-screen grid content-end">
      <div 
        class="animate__animated animate__fadeInUpBig text-gray-100 text-center bg-gray-800 bg-opacity-50 backdrop-blur-sm rounded-t-3xl px-6 py-10">
        
        <h1 class="tangerine-font text-title font-bold" style="font-size:44px!important">{{ couples.join(' & ') }}</h1>
        <decoration class="fill-amber-400 mx-auto w-3/12 mb-3"></decoration>
        <p class="text-sm">
          <p class="font-medium">
            Aşkla çıktık yola❤ </br>
Hasret erdi vuslata💑</br>
Menzilimiz sonsuza🧿</br>
Ey Dostlar, kulak verin nidamıza📣</br>
Bu mutlu günümüzde olun Sizler de yanımızda🇹🇷  
          </p>
          <small>04 Ağustos 2025 18:00</small>
        </p>
      </div>
    </section>
  </section>
</template>

<script setup>

import { computed } from 'vue'
import { useRoute } from 'vue-router'
import decoration from '@/assets/svg/decoration-2.svg'

const couples = ['Mehmet', 'Malika']

const route = useRoute()
let query = computed(() => route.query)

if ( route.query.to === undefined ) query = { to: 'Saudara/i' }

</script>
