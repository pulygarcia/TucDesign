<script setup lang="ts">
import Header from '@/components/base/Header.vue'
import Footer from '@/components/base/Footer.vue'
import TextScroll from '@/components/TextScroll.vue'
import FAQ from '@/components/FAQ.vue'
import { useTitleAnimation } from '@/composables/useTitleAnimation'
import { ref } from 'vue'

const titleRef1 = ref<HTMLElement | null>(null)
const titleRef2 = ref<HTMLElement | null>(null)
const titleRef3= ref<HTMLElement | null>(null)
const titleRef4 = ref<HTMLElement | null>(null)
const imageRef4 = ref<HTMLElement | null>(null)
const cardsRef = ref<HTMLElement | null>(null);
useTitleAnimation(titleRef1, 0.5)
useTitleAnimation(imageRef4, 1)
useTitleAnimation(titleRef2, 0.5)
useTitleAnimation(titleRef3, 0.5)
useTitleAnimation(titleRef4, 1)
useTitleAnimation(cardsRef, 1)

</script>

<template>
  <Header/>
  
  <section class="px-5 relative md:px-20 py-10 md:pt-20 lg:pt-40">
    <div
      class="absolute z-0 inset-0 h-full w-full   bg-[radial-gradient(theme(colors.gray.300)_1px,transparent_1px)] [background-size:16px_16px]"
    ></div>
    <div class="grid grid-cols-12 gap-4 relative z-10">
      <div class="col-span-12 md:col-span-3 my-5 mt-2">
        <p class="h-[1px] bg-black"></p>
        <p class="text-sm">Ponete en Contacto con Tucumán Design</p>
      </div>
      <h1 ref="titleRef2" class="col-span-12 md:col-span-9 text-2xl md:text-3xl lg:text-4xl">
        ¿Tenés dudas o querés transformar tu espacio y no sabes como empezar? 
      </h1>
    </div>
    <h1 ref="titleRef3" class="relative z-10 text-2xl  md:text-3xl lg:text-4xl">
      Nuestro equipo está listo para ayudarte a diseñar el hogar de tus sueños. 
      Contactanos para asesoramiento personalizado en arquitectura, interiorismo y mobiliario.
    </h1>
  </section>
  <section ref="cardsRef" class="grid pb-20 grid-cols-12 gap-5 overflow-hidden px-5 relative md:px-20">
    <div
      class="absolute z-0 inset-0 h-full w-full   bg-[radial-gradient(theme(colors.gray.300)_1px,transparent_1px)] [background-size:16px_16px]"
    ></div>
    <div class="relative z-10 col-span-12 md:col-span-4 lg:col-span-3 p-5 bg-black/5 cursor-pointer hover:bg-black/10 transition rounded-md ">
      <div class="flex justify-center flex-col items-center space-y-3">
        <h1 class="text-xl">Números de teléfono</h1>
        <ul>
          <li><a href="https://wa.me/3815429673?text=Hola vengo desde el sitio web" class="text-blue-600 underline">3815429673</a></li>
          <li><a href="https://wa.me/3815429673?text=Hola vengo desde el sitio web" class="text-blue-600 underline">3815429673</a></li>
        </ul>
      </div>
    </div>
    <div class="relative z-10 col-span-12 md:col-span-4 lg:col-span-3 p-5 bg-black/5 cursor-pointer hover:bg-black/10 transition rounded-md ">
      <div class="flex justify-center flex-col items-center space-y-3">
        <h1 class="text-xl">Correo electrónico</h1>
        <ul>
          <li>tucumandesign@gmail.com</li>
        </ul>
      </div>
    </div>
    <div class="relative z-10 col-span-12 md:col-span-4 lg:col-span-3 p-5 bg-black/5 cursor-pointer hover:bg-black/10 transition rounded-md ">
      <div class="flex justify-center flex-col items-center space-y-3">
        <h1 class="text-xl">Ubicación del local</h1>
        <p class="flex gap-2 items-center"><span><svg  xmlns="http://www.w3.org/2000/svg"  width="24"  height="24"  viewBox="0 0 24 24"  fill="none"  stroke="#ff0000"  stroke-width="2"  stroke-linecap="round"  stroke-linejoin="round"  class="icon icon-tabler icons-tabler-outline icon-tabler-map-pin"><path stroke="none" d="M0 0h24v24H0z" fill="none"/><path d="M9 11a3 3 0 1 0 6 0a3 3 0 0 0 -6 0" /><path d="M17.657 16.657l-4.243 4.243a2 2 0 0 1 -2.827 0l-4.244 -4.243a8 8 0 1 1 11.314 0z" /></svg></span> Avellaneda 362</p>
        <p>Concepción - Tucumán</p>
      </div>
    </div>
    <div class="relative z-10 col-span-12 md:col-span-4 lg:col-span-3 p-5 bg-black/5 cursor-pointer hover:bg-black/10 transition rounded-md ">
      <div class="flex justify-center flex-col items-center space-y-3">
        <h1 class="text-xl">Redes sociales</h1>
        <ul>
          <li><a href="https://www.instagram.com/tucumandesign/">Instagram</a></li>
          <li><a href="https://www.facebook.com/tucumandesign?locale=es_LA">Facebook</a></li>
        </ul>
      </div>
    </div>
  </section>
  <section ref="titleRef4" class="flex flex-col md:flex-row gap-5 overflow-hidden px-5 relative md:px-20">
  <!-- map -->
  <div class="w-full md:w-1/2 rounded-lg relative z-10">
    <iframe 
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3543.892234622653!2d-65.59817942350354!3d-27.347837411526832!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x9423cf6790c4488b%3A0x1b22b5798a8bef27!2sShipton%201645%2C%20T4146%20Concepci%C3%B3n%2C%20Tucum%C3%A1n!5e0!3m2!1ses-419!2sar!4v1742325586858!5m2!1ses-419!2sar"
      class="w-full h-64 md:h-full"
      style="border:0;"
      loading="lazy"
      referrerpolicy="no-referrer-when-downgrade">
    </iframe>
  </div>

  <!-- local image -->
  <div class="w-full md:w-1/2 rounded-lg relative z-10">
    <img src="../assets/local.jpg" alt="Local" class="w-full h-64 md:h-full object-cover rounded-lg">
  </div>
</section>

  <TextScroll/>
  <FAQ/>
  <Footer/>
</template>
<style>
.bg-gray{
  background: hsl(0, 0%, 96%);
}
.img-card-home{
  @apply rounded-lg object-cover h-full w-full absolute;
}

</style>