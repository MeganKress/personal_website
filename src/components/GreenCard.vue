<script setup>
import { ref } from 'vue'

defineProps({
  name: String,
  image: String,
  project_requirements: String,
  approach: String,
  code: String,
  technology_stack: String,
  date: String,
  service: String,
  url: String
})

</script>

<template>
  <div class="bg-green-200 p-4 rounded-lg m-4 shadow-green-300/50 shadow-md">
    <h1 class="text-xl">{{ name }}</h1>

    <p class="whitespace-pre-line mt-5"><span class="font-bold">Project Requirements: </span>{{ project_requirements }}</p>
    <p class="whitespace-pre-line mt-1"><span class="font-bold">Approach: </span>{{ approach }}</p>
    <p class="whitespace-pre-line mt-1"><span class="font-bold">Code: </span><a :href="code" class="underline text-m hover:text-green-500 mt-5" target="_blank" v-if="code">GitHub</a></p>
    <p class="whitespace-pre-line mt-1"><span class="font-bold">Technology Stack: </span>{{ technology_stack }}</p>
    <p class="whitespace-pre-line mt-1"><span class="font-bold">Date: </span>{{ date }}</p>
    
    <a :href="url" class="underline text-m hover:text-green-500 mt-5" target="_blank" v-if="url">Visit Site</a>
  </div>
</template>

<style scoped>
</style>