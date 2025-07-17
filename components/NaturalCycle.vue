<template>
  <section
    class="container mx-auto bg-[url('/img/padrao.svg')] bg-contain bg-center bg-no-repeat mb-12 sm:mb-16 sm:py-16"
  >
    <p
      class="mb-4 text-center text-balance text-verde-200 uppercase tracking-widest text-sm"
    >
      Natural Cycle
    </p>
    <h2
      class="mb-8 mx-auto font-serif text-balance text-center max-w-screen-md text-white text-4xl sm:text-6xl"
    >
      Rhythm of the Forest
    </h2>
    <div class="flex flex-col gap-4 sm:flex-row sm:gap-8">
      <div
        v-for="cycle in naturalCycle"
        :key="cycle.title"
        class="grid flex-1 gap-4 bg-verde-900 p-6 sm:p-8 rounded-xl transition-transform"
        :class="{
          'sm:hover:-translate-y-2': cycle.title !== 'Midday',
          'sm:translate-y-12 sm:hover:translate-y-10':
            cycle.title === 'Midday',
        }"
      >
        <div class="neon size-10 flex items-center justify-center">
          <img :src="cycle.icon" alt="" />
        </div>
        <h3 class="font-serif text-2xl text-white">
          {{ cycle.title }}
        </h3>
        <p class="text-gray-400">{{ cycle.description }}</p>
        <span class="text-verde-300">{{ cycle.time }}</span>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const naturalCycle = [
  {
    title: 'Dawn',
    description:
      'Wake up to birdsong and join our outdoor walks.',
    time: '05:40 - 07:00',
    icon: '/img/manha.svg',
  },
  {
    title: 'Midday',
    description:
      'Explore our shaded trails and enjoy a gourmet picnic in nature.',
    time: '12:00 - 14:00',
    icon: '/img/dia.svg',
  },
  {
    title: 'Night',
    description:
      'End your day with our stargazing session.',
    time: '19:00 - 21:00',
    icon: '/img/noite.svg',
  },
]
</script>
