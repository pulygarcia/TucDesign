<script setup lang="ts">
import { ref } from 'vue'
import Header from "@/components/base/Header.vue"
import Footer from '@/components/base/Footer.vue'
import { useTitleAnimation } from '@/composables/useTitleAnimation'
import { useParagraphAnimation } from '@/composables/useParagraphAnimation'
import IconArrowGrowUp from '../components/icons/IconArrowGrowUp.vue'

const titleRef1 = ref<HTMLElement | null>(null)
const titleRef2 = ref<HTMLElement | null>(null)
const titleRef3= ref<HTMLElement | null>(null)
const titleRef4 = ref<HTMLElement | null>(null)
const imageRef4 = ref<HTMLElement | null>(null)
const paragraphRef = ref<HTMLElement | null>(null)
const cardsRef = ref<HTMLElement | null>(null)
const cardHistory = ref<HTMLElement | null>(null)
const cultureRefTitle = ref<HTMLElement | null>(null)
const cultureCardsRef = ref<HTMLElement | null>(null)
const economicTitleRef = ref<HTMLElement | null>(null)
const economicParagraphRef = ref<HTMLElement | null>(null)
const economicCardImgRef = ref<HTMLElement | null>(null)

useTitleAnimation(titleRef1, 0.5)
useTitleAnimation(imageRef4, 1)
useTitleAnimation(titleRef2, 0.5)
useTitleAnimation(titleRef3, 0.5)
useTitleAnimation(titleRef4, 1)
useTitleAnimation(cardsRef, .5)
useTitleAnimation(cardHistory, .5)
useParagraphAnimation(paragraphRef, .5)
useTitleAnimation(cultureRefTitle, .3)
useParagraphAnimation(cultureCardsRef, .4)
useParagraphAnimation(economicTitleRef, .3)
useParagraphAnimation(economicParagraphRef, .4)
useParagraphAnimation(economicCardImgRef, .2)
</script>

<template>
  <Header class="header w-full h-full" />
  <main class="w-full relative px-5 md:px-20 py-10 md:py-20 lg:py-28">
    <div
      class="absolute z-0 inset-0 h-full w-full bg-[radial-gradient(theme(colors.gray.200)_1px,transparent_1px)] [background-size:16px_16px]"
    ></div>
    <main>
      <div class="relative w-full flex flex-col">
        <h2 ref="titleRef1" class="text-2xl md:text-5xl relative z-10 my-10">Acerca de Tucumán Design</h2>
        <div class="grid relative lg:space-x-20 z-40 grid-cols-12">
          <div ref="cardsRef" class="col-span-12 md:col-span-6">
            <img src="@/assets/scroll-image-2.png" alt="tucuman design local" class="w-full rounded-lg">
          </div>
          <div class="col-span-12 md:col-span-6">
            <h2 ref="titleRef2" class="text-3xl md:text-4xl text-wrap">Todo lo que necesitas saber</h2>
            <p ref="paragraphRef" class="text-lg md:text-lg mt-10 text-wrap">
              Tucumán Design es un estudio de arquitectura e interiorismo ubicado en Concepción, Tucumán. Dirigido por Guillermo Argañaraz,
              arquitecto, diseñador y fundador. Con una visión innovadora y un enfoque en la calidad,
              Guillermo lidera cada proyecto, asegurando que cada espacio refleje funcionalidad, estética y personalidad.
              Nos especializamos en transformar ideas en realidades únicas, creando ambientes que inspiran y mejoran la vida de nuestros clientes.
            </p>
            <a href="https://wa.me/3815429673?text=Hola%2C%20vengo%desde%el%sitio%web%">
              <button
                ref="buttonRef"
                class="bg-black inline-flex gap-2 text-white py-4 px-5 mt-12 rounded-lg">
                Contactar
                <IconArrowGrowUp/>
              </button>
            </a>
          </div>
        </div>
      </div>
    </main>
    <div class="relative">
  <h2 ref="cultureRefTitle" class="text-3xl md:text-5xl relative z-10 my-10">¿Qué trabajos realizamos?</h2>
  <div ref="cultureCardsRef" class="grid relative md:gap-10 z-40 grid-cols-12">
    <div class="col-span-12 md:col-span-3 relative cursor-pointer">
      <div class="container-img-culture">
        <img src="@/assets/scroll-image-1.jpg" alt="Diseño de interiores" class="img-culture">
      </div>
      <div class="p-5 relative z-20 flex flex-col w-full">
        <h1 class="text-xl">Interiorismo</h1>
        <p class="text-sm">
          Diseñamos y transformamos espacios interiores con una visión moderna y funcional, combinando estética y comodidad para reflejar la esencia de cada cliente.
        </p>
      </div>
    </div>

    <div class="col-span-12 md:col-span-3 relative cursor-pointer">
      <div class="container-img-culture">
        <img src="@/assets/about.jpg" alt="Planificación de espacios" class="img-culture">
      </div>
      <div class="p-5 relative z-20 flex flex-col w-full">
        <h1 class="text-xl">Planificación</h1>
        <p class="text-sm">
          Elaboramos proyectos arquitectónicos y de interiorismo detallados, asegurando funcionalidad, armonía y optimización de cada ambiente.
        </p>
      </div>
    </div>

    <div class="col-span-12 md:col-span-3 relative cursor-pointer">
      <div class="container-img-culture">
        <img src="@/assets/scroll-image-3.jpg" alt="Muebles y diseño" class="img-culture">
      </div>
      <div class="p-5 relative z-20 flex flex-col w-full">
        <h1 class="text-xl">Amoblamiento</h1>
        <p class="text-sm">
          Ofrecemos muebles exclusivos y personalizados, diseñados para complementar cada espacio con calidad, estilo y funcionalidad.
        </p>
      </div>
    </div>

    <div class="col-span-12 md:col-span-3 relative cursor-pointer">
      <div class="container-img-culture">
        <img src="@/assets/scroll-image-4.jpg" alt="Asesoramiento en diseño" class="img-culture">
      </div>
      <div class="p-5 relative z-20 flex flex-col w-full">
        <h1 class="text-xl">Asesoramiento personalizado</h1>
        <p class="text-sm">
          Brindamos acompañamiento experto en diseño y arquitectura, ayudándote a tomar las mejores decisiones para optimizar y embellecer tus espacios.
        </p>
      </div>
    </div>

    </div>
  </div>

    <div class="relative z-10 pt-32 w-full">
      <div class="grid relative md:gap-10 z-40 grid-cols-12">
        <div class="col-span-12 md:col-span-6">
          <h2 ref="economicTitleRef" class="text-3xl md:text-5xl relative z-10">Local físico</h2>
          <p ref="economicParagraphRef" class="text-lg md:text-lg mt-10">
            Contamos con un local y oficina para que puedas acercarte personalmente a realizar cualquier consulta y ser atendido de la mejor manera.
            Aquí podrás ver nuestros diseños, mobiliario y materiales en persona.  
            Te invitamos a visitarnos y recibir asesoramiento directo de nuestro equipo liderado por  
            <strong>Guillermo Argañaraz</strong>, arquitecto, diseñador y dueño, quien dirige cada detalle de nuestros proyectos.
          </p>
        </div>
        <div ref="economicCardImgRef" class="col-span-12 md:col-span-6">
          <img src="@/assets/scroll-image-5.jpg" alt="juego de living" class="rounded-lg max-h-[30rem] w-full object-cover">
        </div>
      </div>
    </div>
    <div class="relative z-10 pt-32 w-full">
      <div class="grid relative md:gap-10 z-40 grid-cols-12">
        <div class="col-span-12 md:col-span-6">
          <img src="@/assets/garantia.jpg" alt="arquitecto" class="rounded-lg max-h-[30rem] w-full object-cover">
        </div>
        <div class="col-span-12 md:col-span-6">
          <h2 ref="" class="text-3xl md:text-5xl relative z-10">Garantía</h2>
          <p ref="" class="text-lg md:text-lg mt-10">
            Todos nuestros trabajos cuentan con una garantía extendida y pactada por el cliente y el arquitecto.
          </p>
        </div>
      </div>
    </div>
  </main>
  <Footer />
</template>


<style>
.img-culture{
  @apply rounded-lg w-full h-full overflow-hidden object-cover transition-transform duration-300 ease-in-out transform hover:scale-110
}
.container-img-culture{
  @apply relative h-64 w-full overflow-hidden rounded-lg
}
</style>