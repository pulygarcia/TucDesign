<script setup lang="ts">
import Header from '@/components/base/Header.vue'
import Footer from '@/components/base/Footer.vue'
import ImageBanner from '@/components/ImageBanner.vue'
import image1 from '@/assets/slider-1.jpg'
import image3 from '@/assets/slider-2.jpg'
import image4 from '@/assets/slider-3.jpg'
import SectionHighlight from '@/components/SectionHighlight.vue'
import ScrollTriggerSection from '@/components/ScrollTriggerSection.vue'
import FAQ from '@/components/FAQ.vue'
import MiniCardHome from '@/components/MiniCardHome.vue'
import AnimatedCard from '@/components/AnimatedCard.vue'
import { useTitleAnimation } from '@/composables/useTitleAnimation'
import { useParagraphAnimation } from '@/composables/useParagraphAnimation'
import { ref } from 'vue'

const titleRef1 = ref<HTMLElement | null>(null)
const titleRef2 = ref<HTMLElement | null>(null)
const titleRef3= ref<HTMLElement | null>(null)
const titleRef4 = ref<HTMLElement | null>(null)
const paragraphRef = ref<HTMLElement | null>(null)
const imageRef4 = ref<HTMLElement | null>(null)

useParagraphAnimation(paragraphRef, 0.5)
useTitleAnimation(titleRef1, 0.5)
useTitleAnimation(imageRef4, .5)
useTitleAnimation(titleRef2, 0.5)
useTitleAnimation(titleRef3, 0.5)
useTitleAnimation(titleRef4, .5)
const imagesList = [image1,image3,image4,]
</script>

<template>
  <Header/>
  <AnimatedCard/>
  <MiniCardHome/>
  <SectionHighlight/>
  <main class="relative py-10">
    <ScrollTriggerSection/>
  </main>
  <section class="grid grid-cols-12 md:gap-20 relative py-10 md:py-20 px-5 md:px-20">
    <div ref="imageRef4" class="col-span-12 lg:col-span-6 relative z-30">
      <ImageBanner :images="imagesList" />
    </div>
    <div class="col-span-12 md:col-span-6 relative z-30">
      <div class="flex flex-col w-full h-full">
        <h1 ref="titleRef4" class="text-3xl md:text-3xl lg:text-5xl">
          Experiencia en nuestro trabajo
        </h1>
        <p class="mt-4 text-lg md:text-xl">
          Con años de experiencia en el diseño y la arquitectura, Tucumán Design se ha consolidado como un referente en la creación de espacios excepcionales. Fundado por el reconocido arquitecto y diseñador Guillermo Argañaraz, nuestro negocio ha perfeccionado la capacidad de transformar ideas en realidades tangibles, siempre con un enfoque personalizado y de calidad.
        </p>
      </div>
    </div>
  </section>
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