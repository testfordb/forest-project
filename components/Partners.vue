<template>
  <section
    class="container mx-auto mb-12 sm:mb-16"
  >
    <ul
      class="flex flex-col justify-center items-center py-4 max-sm:divide-y-2 max-sm:divide-verde-900 sm:flex-row sm:gap-8 sm:border-b-2 sm:border-t-2 sm:border-verde-900 sm:py-8"
    >
      <li
        v-for="partner in partners"
        :key="partner.alt"
        class="p-4"
      >
        <img
          :src="partner.src"
          :alt="partner.alt"
          class="max-h-8"
        />
      </li>
    </ul>
  </section>
</template>

<script setup lang="ts">
const partners = [
  { src: '/img/parceiros/caravan.svg', alt: 'Caravan' },
  { src: '/img/parceiros/dogs.svg', alt: 'Dogs' },
  { src: '/img/parceiros/wildbeast.svg', alt: 'Wildbeast' },
  { src: '/img/parceiros/lescone.svg', alt: 'Lescone' },
  { src: '/img/parceiros/surfbot.svg', alt: 'Surfbot' },
]
</script>
