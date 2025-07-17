<template>
  <section
    id="experiencias"
    class="container mx-auto mb-12 sm:mb-16 grid sm:grid-cols-2 gap-8"
  >
    <div class="bg-verde-900 p-6 sm:p-8 rounded-xl">
      <p
        class="mb-4 text-verde-200 uppercase tracking-widest text-sm"
      >
        Exclusive Experiences
      </p>
      <h2
        class="mb-8 font-serif text-white text-3xl sm:text-4xl lg:text-5xl text-balance capitalize"
      >
        Choose Your Next Adventure
      </h2>
      <div v-for="exp in experiences" :key="exp.title">
        <h3
          class="neon-before text-white text-xl flex items-center gap-4 mb-2"
        >
          {{ exp.title }}
        </h3>
        <p
          class="text-gray-400 text-balance mb-8 pl-10"
        >
          {{ exp.description }}
        </p>
      </div>
    </div>
    <div class="grid grid-cols-2 gap-4">
      <div
        v-for="img in experienceImages"
        :key="img.alt"
        class="group relative cursor-pointer overflow-hidden rounded-xl"
        :class="{ 'row-span-2': img.alt === 'Observação Noturna' }"
      >
        <img
          class="size-full object-cover group-hover:scale-110 transition-transform"
          :src="img.src"
          :alt="img.alt"
        />
        <div
          class="absolute flex items-end p-4 inset-0 bg-gradient-to-t from-verde-950/80 opacity-0 group-hover:opacity-100 transition-opacity"
        >
          <span class="text-white">{{ img.alt }}</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const experiences = [
  {
    title: 'Night Observation',
    description:
      'Explore wildlife in its natural habitat under the stars.',
  },
  {
    title: 'Wildlife',
    description: 'Observe wildlife in its natural habitat.',
  },
  {
    title: 'Canoeing',
    description: 'Conquer new horizons with our expert team.',
  },
]

const experienceImages = [
  { src: '/img/canoagem.jpg', alt: 'Canoagem' },
  { src: '/img/observacao-noturna.jpg', alt: 'Observação Noturna' },
  { src: '/img/vida-selvagem.jpg', alt: 'Vida Selvagem' },
]
</script>
