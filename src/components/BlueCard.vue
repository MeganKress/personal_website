<script setup>
import { computed, getCurrentInstance } from 'vue'

const props = defineProps({
  name: String,
  description: String,
  url: String,
  searchTerm: String
})

let hasSearchTerm = computed(() => {
  return props.searchTerm == '' || props.searchTerm == undefined || 
    props.description.toLowerCase().includes(props.searchTerm.toLowerCase()) || 
    props.name.toLowerCase().includes(props.searchTerm.toLowerCase()) ||
    props.url.toLowerCase().includes(props.searchTerm.toLowerCase())
})



</script>

<template>
  <div v-if="this.hasSearchTerm" class="relative bg-blue-100 p-4 rounded-lg m-4 shadow-blue-200/50 shadow-md">
    <h1 class="text-xl mb-5">{{ name }}</h1>

    <p class="whitespace-pre-line mb-5">{{ description }}</p>
    
    <a :href="url" class="absolute bottom-1 underline text-m text-blue-700 hover:text-blue-400 mt-20" target="_blank" v-if="url">Visit Site</a>
    
  </div>
</template>

<style scoped>
</style>