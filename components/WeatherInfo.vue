<template>
  <div class="container mx-auto mt-4 flex justify-center md:justify-start">
    <div class="inline-flex items-center rounded-md bg-verde-900">
      <span class="neon size-2 block relative -left-1"></span>
      <div class="flex text-verde-300 divide-x-2 divide-verde-800">
        <div class="px-4 py-2 capitalize">{{ day }}</div>
        <div class="px-4 py-2">{{ temperature }}</div>
        <div class="px-4 py-2">{{ weather }}</div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const random = Math.floor(Math.random() * 10) + 20
const temperature = ref(`${random}º`)
const weather = ref(random < 25 ? `🌧 ${random + 5}%` : `🌥`)
const day = ref(new Date().toLocaleDateString('en-US', { weekday: 'long' }))
</script>
