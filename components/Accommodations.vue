<template>
  <section
    id="acomodacoes"
    class="radial-gradient container mx-auto grid lg:grid-cols-[2fr_3fr] gap-4 pt-16 mb-12 sm:mb-16"
  >
    <div class="bg-[url('/img/padrao.svg')] bg-no-repeat bg-contain bg-left-top">
      <h2 class="text-white mb-8 text-4xl font-serif lg:text-5xl">
        Natural Retreat
      </h2>
      <ul class="text-gray-200 space-y-4 sm:text-xl">
        <li
          v-for="item in accommodationItems"
          :key="item"
          class="flex items-center gap-4"
        >
          <span class="neon h-0.5 w-6 bg-verde-400 inline-block"></span>
          {{ item }}
        </li>
      </ul>
    </div>
    <div class="grid grid-cols-[2fr_1fr] gap-4 sm:gap-8">
      <div class="col-span-full grid">
        <img
          class="h-52 w-full object-cover rounded-xl"
          src="/img/casa1.jpg"
          alt="Casa 1"
        />
        <span
          class="m-2 self-start justify-self-end uppercase text-white rounded-full bg-verde-950/60 px-4 py-2 text-sm/none"
        >
          Ruby
        </span>
      </div>
      <div class="grid">
        <img
          class="size-full object-cover rounded-xl"
          src="/img/casa2.jpg"
          alt="Casa 2"
        />
        <span
          class="m-2 self-start justify-self-end uppercase text-white rounded-full bg-verde-950/60 px-4 py-2 text-sm/none"
        >
          Emerald
        </span>
      </div>
      <div class="grid">
        <img
          class="size-full object-cover rounded-xl"
          src="/img/casa3.jpg"
          alt="Casa 3"
        />
        <span
          class="m-2 self-start justify-self-end uppercase text-white rounded-full bg-verde-950/60 px-4 py-2 text-sm/none"
        >
          Saphire
        </span>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
const accommodationItems = [
  'Experience nature up close',
  'Connect with nature',
  'Disconnect from the digital world',
  'Observe wildlife',
  'Choose your favorite cabin',
]
</script>
