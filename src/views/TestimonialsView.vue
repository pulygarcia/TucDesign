<script lang="ts" setup>
import { ref, onMounted } from 'vue'
import TestimonialCard from "@/components/TestimonialCard.vue"
import Header from "@/components/base/Header.vue"
import userProfile from '@/assets/user.png'
import Footer from "@/components/base/Footer.vue"
import { gsap } from 'gsap'
const testimonials = ref([
  {
    userImage: userProfile,
    userText: "El equipo de Tucumán Design hizo un trabajo increíble con el local de mi emprendimiento. Súper profesionales y atentos a cada detalle.",
    userName: "Martina López",
    userTitle: "Dueña de Tienda Creativa"
  },
  {
    userImage: userProfile,
    userText: "Necesitaba un diseño moderno para mi restaurante y quedé fascinado con el resultado. Recomiendo 100% a Tucumán Design.",
    userName: "Javier Gómez",
    userTitle: "Propietario de Sabores del Norte"
  },
  {
    userImage: userProfile,
    userText: "Me ayudaron con la identidad visual de mi negocio. El proceso fue súper fácil y entendieron exactamente lo que quería.",
    userName: "Camila Rodríguez",
    userTitle: "Emprendedora"
  },
  {
    userImage: userProfile,
    userText: "Desde el primer contacto, la atención fue excelente. Diseñaron living, comedor y patio de mi casa y quedaron impresionantes. ¡Gracias por todo!",
    userName: "Facundo Herrera",
    userTitle: "Profesor universitario"
  },
  {
    userImage: userProfile,
    userText: "El mejor estudio de diseño de Tucumán. Profesionales, creativos y muy responsables. Sin dudas los volveré a elegir.",
    userName: "Lorena Sosa",
    userTitle: "Gerente de Marketing"
  },
  {
    userImage: userProfile,
    userText: "Hicieron toda la estética para mi empresa y quedé encantado. ¡Superaron mis expectativas!",
    userName: "Matías Fernández",
    userTitle: "Dueño de Ethernal insumos graficos"
  }
]);


const animateText = () => {
  gsap.from(".animated-text", {
    y: 30,
    opacity: 0,
    duration: 1,
    ease: "power2.out",
    stagger: 0.2,
  })
}

const animateCards = () => {
  gsap.from(".testimonial-card", {
    y: 30,
    opacity: 0,
    duration: 0.5,
    ease: "power2.out",
    stagger: 0.2,
  })
}

onMounted(() => {
  animateText();
  animateCards();
});
</script>

<template>
  <main class="min-h-screen">
    <div>
      <Header />
      <div class="relative py-10">
        <div class="pt-5 px-5 md:px-20 relative z-10">
          <h2 class="text-3xl md:text-4xl  my-16">Comentarios de nuestros clientes</h2>
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5">
            <TestimonialCard
              v-for="(testimonial, index) in testimonials"
              :key="index"
              class="testimonial-card"
              :userImage="testimonial.userImage"
              :userText="testimonial.userText"
              :userName="testimonial.userName"
              :userTitle="testimonial.userTitle"
            />
          </div>
        </div>
      </div>
    </div>
  </main>
  <Footer />
</template>
