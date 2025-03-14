<script setup lang="ts">
import img1 from '@/assets/slider-1.jpg'
import img2 from '@/assets/slider-2.jpg'
import img3 from '@/assets/slider-3.jpg'
import img4 from '@/assets/slider-4.jpg'
import img5 from '@/assets/slider-5.jpg'
import img6 from '@/assets/trigger-6.avif'
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'

const cards = [
  {
    title: "Diseño de interiores",
    description: "La combinación perfecta entre estilo y funcionalidad para transformar tus espacios.",
    image: img1,
  },
  {
    title: "Iluminación",
    description: "La luz adecuada para realzar cada detalle y crear ambientes únicos.",
    image: img2,
  },
  {
    title: "Arquitectura",
    description: "Diseño y construcción de espacios innovadores que combinan estética y funcionalidad.",
    image: img3,
  },
  {
    title: "Profesionalismo",
    description: "Contamos con un equipo de expertos que se encarga de hacer realidad cada proyecto,",
    image: img4,
  },
  {
    title: "Muebles",
    description: "Comodidad y diseño en cada detalle. Encuentra el mueble perfecto para tu espacio.",
    image: img5,
  },
  {
    title: "Atención personalizada",
    description: "Cada proyecto es único, y nos aseguramos de darte la atención necesaria para que tus ideas se vean reflejadas en él.",
    image: img6,
  }
]

const cardsRef = ref<HTMLElement[]>([])
const titleRef = ref<HTMLElement | null>(null)
  onMounted(() => {
  const title = titleRef.value;
  const words = title?.innerText.split(' ') || [];
  title!.innerHTML = words.map(word => `<span class="word">${word}</span>`).join(' ');

  const wordElements = title?.querySelectorAll('.word');

  if (wordElements && wordElements.length > 0) {
    gsap.fromTo(
      wordElements,
      { y: '100%', clipPath: 'inset(0 0 100% 0)' },
      {
        y: '0%',
        clipPath: 'inset(0 0 0% 0)',
        duration: 1,
        ease: 'power4.out',
        stagger: 0.2,
      }
    );
  }

  gsap.fromTo(
    cardsRef.value,
    { opacity: 0, y: 50 },
    {
      opacity: 1,
      y: 0,
      duration: 1,
      ease: 'power4.out',
      stagger: 0.2,
    }
  )
})
</script>

<template>
  <section class="flex flex-col w-full px-5 md:px-20 relative ">
    <div
      class="absolute z-0 inset-0 h-full w-full   bg-[radial-gradient(theme(colors.gray.300)_1px,transparent_1px)] [background-size:16px_16px]"
    ></div>
    <p class="relative z-10 ">Bienvenido</p>
    <h1 ref="titleRef" class="text-heading-1 relative z-10 text-black card-title">Explora el universo del diseño y la arquitectura con Tucumán Design.</h1> 
    <div class="grid grid-cols-1 relative z-10 sm:grid-cols-2 lg:grid-cols-3 gap-x-5 gap-y-3 md:gap-y-8 mt-10">
      <div 
        v-for="(card, index) in cards" 
        :key="index" 
        class="p-7 bg-gray hover:bg-black/10 transition rounded-lg group duration-700 cursor-pointer"
      >
        <div ref="cardsRef" class="flex gap-5">
          <div class="md:w-14 h-14 w-20 rounded-lg bg-white relative group-hover:bg-black/10 transition-colors duration-700">
            <img :src="card.image" alt="" class="img-card-home">
          </div>
          <div>
            <h4 class="text-lg md:text-xl ">{{ card.title }}</h4>
            <p class="text-sm md:text-base card-description">{{ card.description }}</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.card-title, .card-description {
  overflow: hidden;
  display: inline-block;
}

.word {
  display: inline-block;
  overflow: hidden;
}
</style>
