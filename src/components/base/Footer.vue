<template>
<footer class="flex w-full mt-20 px-5 md:px-20">
  <div class="w-full  mx-auto p-4 ">
    <div class="sm:flex sm:items-center sm:justify-between">
      <router-link 
        to="/" 
        class="flex items-center mb-5 md:mb-0 rtl:space-x-reverse text-3xl md:text-5xl"
      >
        Tucumán Design
      </router-link>
      <ul class="flex flex-wrap items-center mb-6 text-sm font-medium sm:mb-0 ">
        <li>
          <router-link  to="/about" class="hover:underline me-4 md:me-6">Inicio</router-link>
        </li>
        <li>
          <router-link  to="/contact" class="hover:underline">Contacto</router-link>
        </li>
      </ul>
    </div>
    <hr class="my-6 border-gray-300 sm:mx-auto lg:my-8" />
    <span class="block text-sm sm:text-center">
      © 2025
      <router-link  to="/" class="hover:underline">
        Tucumán Design - 
      </router-link>
      Hecho por <a href="https://portfolio-puly-v4.vercel.app/" class="underline text-blue-600">Puly García</a>
    </span>
  </div>
</footer>
</template>