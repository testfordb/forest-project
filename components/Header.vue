<template>
  <header class="container mx-auto flex items-center justify-between gap-8 py-8">
    <a href="/">
      <img src="/img/forest.svg" alt="Forest" />
    </a>
    <nav
      :class="{ hidden: !isMenuOpen, flex: isMenuOpen }"
      class="items-center lg:block z-40 max-lg:fixed max-lg:w-full max-lg:inset-0"
    >
      <div class="fixed lg:hidden inset-0 bg-verde-950/40 backdrop-blur-md"></div>
      <ul
        class="text-white text-2xl max-lg:divide-y-2 max-lg:divide-white/10 max-lg:z-50 max-lg:absolute max-lg:p-8 max-lg:w-full lg:text-xl lg:flex lg:flex-wrap lg:gap-8"
      >
        <li
          v-for="(item, index) in navItems"
          :key="index"
          :class="`animate-slide-in-${(index + 1) * 100} opacity-0`"
        >
          <a
            :href="item.href"
            class="p-4 lg:px-0 lg:py-2 block max-lg:hover:bg-white/10 lg:hover:underline lg:hover:underline-offset-8"
          >
            {{ item.text }}
          </a>
        </li>
      </ul>
    </nav>
    <button
      @click="toggleMenu"
      class="btn flex items-center gap-3 text-verde-900 py-1 rounded-full lg:hidden"
    >
      Menu
      <span class="h-3 w-4 flex flex-col justify-between">
        <span class="h-0.5 rounded-md bg-verde-800"></span>
        <span class="h-0.5 rounded-md bg-verde-800"></span>
        <span class="h-0.5 rounded-md bg-verde-800"></span>
      </span>
    </button>
  </header>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false)
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const navItems = [
  { text: 'Accommodations', href: '#acomodacoes' },
  { text: 'Events', href: '#eventos' },
  { text: 'Experiences', href: '#experiencias' },
  { text: 'Contact', href: '#contato' },
]
</script>
