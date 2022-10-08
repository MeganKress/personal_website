<script setup>
import { ref } from 'vue'

defineProps({
  name: String,
  description: String,
  url: String,
  points: Array,
})

const count = ref(0)
</script>

<template>
  <div class="bg-yellow-200 p-4 rounded-lg m-4 shadow-yellow-300/50 shadow-md">
    <h1 class="text-xl">{{ name }}</h1>

    <p class="whitespace-pre-line">{{ description }}</p>

    <ul v-for="(point, index) in points" :key="index" class="list-disc ml-8 mt-2">
      <li>{{point}}</li>
    </ul>
    
    <a :href="url" class="underline text-m gray" target="_blank" v-if="url">Visit Site</a>
  </div>
</template>

<style scoped>
</style>