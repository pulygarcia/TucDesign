<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
import IconPlus from './icons/IconPlus.vue'

import { useTitleAnimation } from '@/composables/useTitleAnimation'
import { useParagraphAnimation } from '@/composables/useParagraphAnimation'

const titleRef1 = ref<HTMLElement | null>(null)
const imageRef = ref<HTMLElement | null>(null)
const faqRef = ref<HTMLElement | null>(null)

useParagraphAnimation(titleRef1, .5)
useTitleAnimation(imageRef, 1)
useTitleAnimation(faqRef, 1.5)

const faqs = ref([
  {
    question: "Como puedo cotizar el trabajo que necesito?",
    answer: "Nosotros lo cotizamos ",
    isOpen: false,
  },
  {
    question: "Como puedo cotizar el trabajo que necesito?",
    answer: "Tokyo has an excellent public transportation system, including trains",
    isOpen: false,
  },
  {
    question: "Como puedo cotizar el trabajo que necesito?",
    answer: "Visa ",
    isOpen: false,
  },
  {
    question: "Como puedo cotizar el trabajo que necesito?",
    answer: "Tokyo'",
    isOpen: false,
  },
])

const toggleFaq = (index: number) => {
  faqs.value.forEach((faq, i) => {
    if (i === index) {
      faq.isOpen = !faq.isOpen;
    } else {
      faq.isOpen = false;
    }
  })

  faqs.value.forEach((faq, i) => {
    const answerElement = document.querySelectorAll('.faq-answer')[i];
    if (faq.isOpen) {
      gsap.to(answerElement, { height: 'auto', opacity: 1, duration: 0.5, ease: 'power2.out' });
    } else {
      gsap.to(answerElement, { height: 0, opacity: 0, duration: 0.3, ease: 'power2.in' });
    }
  });
}

onMounted(() => {
  gsap.set('.faq-answer', { height: 0, opacity: 0 });
})
</script>

<template>
  <section>
    <div class="2xl:container 2xl:mx-auto md:py-12 lg:px-20 md:px-6 py-9 px-4">
      <h2 ref="titleRef1" class="lg:text-6xl md:text-4xl text-3xl lg:leading-9 md:leading-7 leading-9">
        Preguntas Frecuentes
      </h2>
      <div class="flex md:flex-row flex-col md:space-x-8 md:mt-16 mt-8">
        <div ref="imageRef" class="md:w-5/12 lg:w-4/12 w-full">
          <img 
            src="https://static-wc.arcux.net/uploads/20200529130551/la-arquitectura-1.jpg" 
            alt="Arquitectura imagen" 
            class="w-full h-[18rem] object-cover rounded-lg" 
          />
        </div>
        <div ref="faqRef" class="md:w-7/12 lg:w-8/12 w-full md:mt-0 sm:mt-14 mt-10">
          <div v-for="(faq, index) in faqs" :key="index">
            <div class="flex justify-between items-center cursor-pointer" @click="toggleFaq(index)">
              <h3 class="text-xl leading-5">{{ faq.question }}</h3>
              <IconPlus/>
            </div>
            <p class="faq-answer text-base leading-6 text-gray-600 mt-4 w-11/12">{{ faq.answer }}</p>
            <hr class="my-7 bg-gray-500" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.faq-answer {
  overflow: hidden;
}
</style>
