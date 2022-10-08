<script setup>
import { ref } from 'vue'

defineProps({
  name: String,
  description: String,
  image: String,
  client: String,
  date: String,
  service: String,
  url: String
})

</script>

<template>
  <div class="bg-green-200 p-4 rounded-lg m-4 shadow-green-300/50 shadow-md">
    <h1 class="text-xl">{{ name }}</h1>

    <img :src="image" class="bg-white p-3 rounded-lg flex mx-auto mt-8 mb-8 h-40">

    <p class="whitespace-pre-line">{{ description }}</p>

    <p class="whitespace-pre-line mt-5"><span class="font-bold">Client: </span>{{ client }}</p>
    <p class="whitespace-pre-line mt-1"><span class="font-bold">Date: </span>{{ date }}</p>
    <p class="whitespace-pre-line mt-1 mb-5"><span class="font-bold">Service: </span>{{ service }}</p>
    
    <a :href="url" class="underline text-m hover:text-green-500 mt-5" target="_blank" v-if="url">Visit Site</a>
  </div>
</template>

<style scoped>
</style>