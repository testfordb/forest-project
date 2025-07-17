<template>
  <div class="text-white relative max-sm:pt-12 pt-64 px-8 max-sm:px-4 pb-8 rounded-2xl overflow-hidden bg-gradient-to-t from-verde-950/80">
    <img
      class="absolute inset-0 size-full object-cover -z-10 animate-fade-in"
      src="/img/floresta.jpg"
      alt="Floresta"
    />
    <video
      :src="videoSrc"
      class="absolute inset-0 size-full object-cover -z-10"
      muted
      autoplay
      playsinline
      loop
      width="1280"
      height="720"
    ></video>
    <div
      class="bg-verde-950/60 rounded-xl flex flex-col items-start gap-2 p-4 mb-8 sm:gap-8 sm:items-center sm:py-1 sm:pl-4 sm:pr-1 sm:bg-verde-950 sm:inline-flex sm:flex-row sm:rounded-full"
    >
      December Bookings Open
      <a class="btn text-verde-900 flex items-center gap-2" href="#">
        Book Now
        <img src="/img/seta.svg" alt="" />
      </a>
    </div>
    <h1
      class="mb-8 font-serif text-balance text-4xl max-w-screen-sm sm:text-5xl sm:mb-20"
    >
      Experience Life in the Forest
    </h1>
    <div class="text-sm sm:flex justify-between items-end">
      <p class="max-sm:mb-4">
        Best Places to Visit
        <a
          class="underline decoration-2 underline-offset-4 hover:no-underline"
          href="#"
          >2049</a
        >
      </p>
      <div>
        <p class="uppercase mb-2">Recommended by</p>
        <p class="flex items-center gap-4">
          <img
            class="w-28"
            src="/img/parceiros/wildbeast.svg"
            alt="Wildbeast"
          />
          <span>|</span>
          National Magazine
        </p>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const random = Math.floor(Math.random() * 10) + 20
const videoSrc = computed(() =>
  random < 25 ? '/video/video_chuva.mp4' : '/video/video_sol.mp4'
)
</script>
