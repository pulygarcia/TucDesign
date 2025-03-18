<script setup lang="ts">
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

gsap.registerPlugin(ScrollTrigger)

const sectionRef = ref<HTMLElement | null>(null)

onMounted(() => {
  const section = sectionRef.value

  if (section) {
    const elements = section.children

    gsap.fromTo(elements[0], 
      { x: -90, opacity: 0 }, 
      { 
        x: 0, 
        opacity: 1, 
        duration: 1, 
        ease: 'power4.out',
        scrollTrigger: {
          trigger: section,
          start: "top bottom", 
          scrub: 1, 
          toggleActions: "play none none reverse",
        },
      }
    )

    gsap.fromTo(elements[1], 
      { x: 300, opacity: 0 }, 
      { 
        x: 0, 
        opacity: 1, 
        duration: 1, 
        ease: 'power4.out',
        scrollTrigger: {
          trigger: section,
          start: "top bottom",  
          scrub: 1, 
          toggleActions: "play none none reverse",
        }
      }
    )
  }
})
</script>

<template>
  <section ref="sectionRef" class="px-5 md:px-20 lg:gap-20 gap-5 grid bg-black py-5 md:py-10 grid-cols-12 min-h-96 mt-40 w-full overflow-hidden">
    <div class="col-span-12 md:col-span-7 mb-5">
      <div class="text-white flex justify-between text-xs">
        <p>Conocé Tucumán Design</p>
        <p>Reflejá tus ideas en cualquier espacio</p>
      </div>
      <h1 class="text-heading-1 mt-20">Conocé la esencia de Tucumán Design</h1>
      <p class="text-lg md:text-xl text-white my-10">
        Tucumán Design es un espacio donde la creatividad no tiene límites, constantemente revelando nuevas formas de transformar tu hogar y oficina con diseños innovadores. Fundado por el arquitecto y diseñador Guillermo Argañaraz, quien trae con el nuevas ideas y tendencias que marcan la diferencia. Desde las últimas colecciones de muebles hasta soluciones arquitectónicas personalizadas que se adaptan a las necesidades del momento, Guillermo y su equipo aseguran que cada proyecto sea una obra única.
      </p>
      <button class="bg-white py-3 px-5 rounded-md mt-5">Contactar</button>
    </div>
    <div class="col-span-12 md:col-span-5 flex flex-col w-full h-full relative">
      <img src="@/assets/local.jpg" alt="" class="rounded-lg my-20 h-full w-full object-cover">
    </div>
  </section>
</template>

<style scoped>
</style>
