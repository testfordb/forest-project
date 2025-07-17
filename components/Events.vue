<template>
  <section
    id="eventos"
    class="mb-12 sm:mb-16 py-12 sm:py-16 bg-verde-900"
  >
    <div class="container mx-auto">
      <p
        class="mb-4 text-center text-verde-200 uppercase tracking-widest text-sm"
      >
        Connect with Nature
      </p>
      <h2
        class="mb-8 text-balance mx-auto text-center max-w-screen-md text-white text-4xl sm:text-6xl"
      >
        Every Sound, Every Moment, A New Discovery
      </h2>
      <div
        class="overflow-x-auto snap-x snap-mandatory pb-4 grid grid-cols-[repeat(3,minmax(300px,1fr))] gap-4 sm:gap-8"
      >
        <div
          v-for="event in events"
          :key="event.title"
          class="snap-center grid gap-4 bg-verde-800 p-6 sm:p-8 rounded-xl"
        >
          <h3 class="text-verde-300 text-2xl font-serif">
            {{ event.title }}
          </h3>
          <div class="text-white">
            <p class="font-serif text-5xl">{{ event.day }}</p>
            <p class="text-xl">{{ event.date }}</p>
          </div>
          <p class="text-gray-300 text-balance">{{ event.description }}</p>
          <a
            class="justify-self-start self-end btn"
            :href="event.href"
          >
            Book {{ event.day }}/{{ event.month }}
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const events = [
  {
    title: 'New Moon',
    day: '23',
    date: 'March 2049',
    month: '03',
    description:
      'Best time for stargazing. The sky will be clear and the stars visible.',
    href: '#contato',
  },
  {
    title: 'Meteor Shower',
    day: '15',
    date: 'August 2049',
    month: '08',
    description:
      'Best time to observe the meteor shower. The sky will be lit up by stars.',
    href: '#contato',
  },
  {
    title: 'Aurora Borealis',
    day: '15',
    date: 'April 2049',
    month: '04',
    description:
      'Best time to observe the Aurora Borealis. The sky will be illuminated by stars.',
    href: '#contato',
  },
]
</script>
