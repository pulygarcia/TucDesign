<script setup lang="ts">
import { ref } from 'vue'
import Header from "@/components/base/Header.vue"
import Footer from '@/components/base/Footer.vue'
import ProjectCard from '@/components/ProjectCard.vue'

import img1 from '@/assets/scroll-image-1.jpg'
import img2 from '@/assets/luxur-hotel2.avif'
import img3 from '@/assets/project-kitchen.jpg'
import { useTitleAnimation } from '@/composables/useTitleAnimation'
import { useParagraphAnimation } from '@/composables/useParagraphAnimation'

const titleRef1 = ref<HTMLElement | null>(null)
const titleRef2 = ref<HTMLElement | null>(null)
const titleRef3= ref<HTMLElement | null>(null)
const titleRef4 = ref<HTMLElement | null>(null)
const cards1Ref1 = ref<HTMLElement | null>(null)
const cards1Ref2 = ref<HTMLElement | null>(null)
const cards1Ref3 = ref<HTMLElement | null>(null)
const cards1Ref4 = ref<HTMLElement | null>(null)


useTitleAnimation(titleRef1, 0.2)
useTitleAnimation(titleRef2, 0.2)
useTitleAnimation(titleRef3, 0.2)
useTitleAnimation(titleRef4, .3)
useParagraphAnimation(cards1Ref1, .5)
useParagraphAnimation(cards1Ref2, .5)
useParagraphAnimation(cards1Ref3, .5)
useParagraphAnimation(cards1Ref4, .5)
const hotelsAccommodations = [
  {
    img: img1,
    title: "Oficina de consultoría legal"
  },
  {
    img: img2,
    title: "Entrada Hotel Hilton"
  },
  {
    img: img3,
    title: "Cocina moderna minimalista"
  },
]
</script>

<template>
  <Header class="header w-full h-full" />
  <main class="w-full relative px-5 md:px-20 py-10 md:py-20 lg:py-28">
    <div class="relative">
      <h2 ref="titleRef3" class="text-3xl md:text-4xl relative z-10 my-10">
        Algunos de nuestros trabajos terminados
      </h2>
      <div ref="cards1Ref3" class="grid relative md:gap-10 z-40 grid-cols-12">
        <div 
          v-for="(attraction, index) in hotelsAccommodations" 
          :key="index" 
          class="col-span-12 md:col-span-4 lg:col-span-3"
        >
          <ProjectCard 
            :image="attraction.img"
            :title="attraction.title"
          />
        </div>
      </div>
    </div>
  </main>
  <Footer />
</template>
<style scoped>

</style>