<script setup lang="ts">
import { defineProps } from 'vue'
import IconFinished from '@/components/icons/IconFinished.vue';

const props = defineProps<{
  image: string
  title: string
}>()
</script>

<template>
  <figure class="p-2 relative overflow-hidden group">
    <div class="relative overflow-hidden w-full h-64 rounded-lg">
      <img 
        :src="image" 
        class="rounded-lg w-full h-full object-cover" 
        :alt="title"
      >
    </div>
    <figcaption class="outside">
      <div class="flex justify-between px-2 mt-5">
        <h3 class="text-lg">{{ title }}</h3>
        <div class="flex items-center">
          <IconFinished class="text-yellow-500"/>
        </div>
      </div>
    </figcaption>
  </figure>
</template>

<style scoped>

</style>
