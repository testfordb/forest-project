<template>
  <div class="bg-verde-800 font-sans text-white scroll-smooth">
    <!-- Weather Info -->
    <div class="container mx-auto mt-4 flex justify-center md:justify-start">
      <div class="inline-flex items-center rounded-md bg-verde-900">
        <span class="neon size-2 block relative -left-1"></span>
        <div class="flex text-verde-300 divide-x-2 divide-verde-800">
          <div class="px-4 py-2 capitalize" v-text="day"></div>
          <div class="px-4 py-2" v-text="temperature"></div>
          <div class="px-4 py-2" v-text="weather"></div>
        </div>
      </div>
    </div>

    <!-- Header -->
    <header class="container mx-auto flex items-center justify-between gap-8 py-8">
      <a href="/">
        <img src="/img/forest.svg" alt="Forest" />
      </a>
      <nav :class="{ 'hidden': !isMenuOpen, 'flex': isMenuOpen }" class="items-center lg:block z-40 max-lg:fixed max-lg:w-full max-lg:inset-0">
        <div class="fixed lg:hidden inset-0 bg-verde-950/40 backdrop-blur-md"></div>
        <ul class="text-white text-2xl max-lg:divide-y-2 max-lg:divide-white/10 max-lg:z-50 max-lg:absolute max-lg:p-8 max-lg:w-full lg:text-xl lg:flex lg:flex-wrap lg:gap-8">
          <li v-for="(item, index) in navItems" :key="index" :class="`animate-slide-in-${(index + 1) * 100} opacity-0`">
            <a :href="item.href" class="p-4 lg:px-0 lg:py-2 block max-lg:hover:bg-white/10 lg:hover:underline lg:hover:underline-offset-8">
              {{ item.text }}
            </a>
          </li>
        </ul>
      </nav>
      <button @click="toggleMenu" class="btn flex items-center gap-3 text-verde-900 py-1 rounded-full lg:hidden">
        Menu
        <span class="h-3 w-4 flex flex-col justify-between">
          <span class="h-0.5 rounded-md bg-verde-800"></span>
          <span class="h-0.5 rounded-md bg-verde-800"></span>
          <span class="h-0.5 rounded-md bg-verde-800"></span>
        </span>
      </button>
    </header>

    <!-- Main Hero -->
    <main class="container mx-auto">
      <div class="text-white relative max-sm:pt-12 pt-64 px-8 max-sm:px-4 pb-8 rounded-2xl overflow-hidden bg-gradient-to-t from-verde-950/80">
        <img class="absolute inset-0 size-full object-cover -z-10 animate-fade-in" src="/img/floresta.jpg" alt="Floresta" />
        <video :src="videoSrc" class="absolute inset-0 size-full object-cover -z-10" muted autoplay playsinline loop width="1280" height="720"></video>
        <div class="bg-verde-950/60 rounded-xl flex flex-col items-start gap-2 p-4 mb-8 sm:gap-8 sm:items-center sm:py-1 sm:pl-4 sm:pr-1 sm:bg-verde-950 sm:inline-flex sm:flex-row sm:rounded-full">
          December Bookings Open
          <a class="btn text-verde-900 flex items-center gap-2" href="#">
            Book Now
            <img src="/img/seta.svg" alt="" />
          </a>
        </div>
        <h1 class="mb-8 font-serif text-balance text-4xl max-w-screen-sm sm:text-5xl sm:mb-20">
          Experience Life in the Forest
        </h1>
        <div class="text-sm sm:flex justify-between items-end">
          <p class="max-sm:mb-4">
            Best Places to Visit
            <a class="underline decoration-2 underline-offset-4 hover:no-underline" href="#">2049</a>
          </p>
          <div>
            <p class="uppercase mb-2">Recommended by</p>
            <p class="flex items-center gap-4">
              <img class="w-28" src="/img/parceiros/wildbeast.svg" alt="Wildbeast" />
              <span>|</span>
              National Magazine
            </p>
          </div>
        </div>
      </div>
    </main>

    <!-- Acomodações -->
    <section id="acomodacoes" class="radial-gradient container mx-auto grid lg:grid-cols-[2fr_3fr] gap-4 pt-16 mb-12 sm:mb-16">
      <div class="bg-[url('/img/padrao.svg')] bg-no-repeat bg-contain bg-left-top">
        <h2 class="text-white mb-8 text-4xl font-serif lg:text-5xl">Natural Retreat</h2>
        <ul class="text-gray-200 space-y-4 sm:text-xl">
          <li v-for="item in accommodationItems" :key="item" class="flex items-center gap-4">
            <span class="neon h-0.5 w-6 bg-verde-400 inline-block"></span>
            {{ item }}
          </li>
        </ul>
      </div>
      <div class="grid grid-cols-[2fr_1fr] gap-4 sm:gap-8">
        <div class="col-span-full grid">
          <img class="h-52 w-full object-cover rounded-xl" src="/img/casa1.jpg" alt="Casa 1" />
          <span class="m-2 self-start justify-self-end uppercase text-white rounded-full bg-verde-950/60 px-4 py-2 text-sm/none">Ruby</span>
        </div>
        <div class="grid">
          <img class="size-full object-cover rounded-xl" src="/img/casa2.jpg" alt="Casa 2" />
          <span class="m-2 self-start justify-self-end uppercase text-white rounded-full bg-verde-950/60 px-4 py-2 text-sm/none">Emerald</span>
        </div>
        <div class="grid">
          <img class="size-full object-cover rounded-xl" src="/img/casa3.jpg" alt="Casa 3" />
          <span class="m-2 self-start justify-self-end uppercase text-white rounded-full bg-verde-950/60 px-4 py-2 text-sm/none">Saphire</span>
        </div>
      </div>
    </section>

    <!-- Eventos -->
    <section id="eventos" class="mb-12 sm:mb-16 py-12 sm:py-16 bg-verde-900">
      <div class="container mx-auto">
        <p class="mb-4 text-center text-verde-200 uppercase tracking-widest text-sm">Connect with Nature</p>
        <h2 class="mb-8 text-balance mx-auto text-center max-w-screen-md text-white text-4xl sm:text-6xl">
          Every Sound, Every Moment, A New Discovery
        </h2>
        <div class="overflow-x-auto snap-x snap-mandatory pb-4 grid grid-cols-[repeat(3,minmax(300px,1fr))] gap-4 sm:gap-8">
          <div v-for="event in events" :key="event.title" class="snap-center grid gap-4 bg-verde-800 p-6 sm:p-8 rounded-xl">
            <h3 class="text-verde-300 text-2xl font-serif">{{ event.title }}</h3>
            <div class="text-white">
              <p class="font-serif text-5xl">{{ event.day }}</p>
              <p class="text-xl">{{ event.date }}</p>
            </div>
            <p class="text-gray-300 text-balance">{{ event.description }}</p>
            <a class="justify-self-start self-end btn" :href="event.href">Book {{ event.day }}/{{ event.month }}</a>
          </div>
        </div>
      </div>
    </section>

    <!-- Experiências -->
    <section id="experiencias" class="container mx-auto mb-12 sm:mb-16 grid sm:grid-cols-2 gap-8">
      <div class="bg-verde-900 p-6 sm:p-8 rounded-xl">
        <p class="mb-4 text-verde-200 uppercase tracking-widest text-sm">Exclusive Experiences</p>
        <h2 class="mb-8 font-serif text-white text-3xl sm:text-4xl lg:text-5xl text-balance capitalize">
          Choose Your Next Adventure
        </h2>
        <div v-for="exp in experiences" :key="exp.title">
          <h3 class="neon-before text-white text-xl flex items-center gap-4 mb-2">{{ exp.title }}</h3>
          <p class="text-gray-400 text-balance mb-8 pl-10">{{ exp.description }}</p>
        </div>
      </div>
      <div class="grid grid-cols-2 gap-4">
        <div v-for="img in experienceImages" :key="img.alt" class="group relative cursor-pointer overflow-hidden rounded-xl" :class="{ 'row-span-2': img.alt === 'Observação Noturna' }">
          <img class="size-full object-cover group-hover:scale-110 transition-transform" :src="img.src" :alt="img.alt" />
          <div class="absolute flex items-end p-4 inset-0 bg-gradient-to-t from-verde-950/80 opacity-0 group-hover:opacity-100 transition-opacity">
            <span class="text-white">{{ img.alt }}</span>
          </div>
        </div>
      </div>
    </section>

    <!-- Ciclo Natural -->
    <section class="container mx-auto bg-[url('/img/padrao.svg')] bg-contain bg-center bg-no-repeat mb-12 sm:mb-16 sm:py-16">
      <p class="mb-4 text-center text-balance text-verde-200 uppercase tracking-widest text-sm">Natural Cycle</p>
      <h2 class="mb-8 mx-auto font-serif text-balance text-center max-w-screen-md text-white text-4xl sm:text-6xl">
        Rhythm of the Forest
      </h2>
      <div class="flex flex-col gap-4 sm:flex-row sm:gap-8">
        <div v-for="cycle in naturalCycle" :key="cycle.title" class="grid flex-1 gap-4 bg-verde-900 p-6 sm:p-8 rounded-xl transition-transform" :class="{
          'sm:hover:-translate-y-2': cycle.title !== 'Meio-dia',
          'sm:translate-y-12 sm:hover:translate-y-10': cycle.title === 'Meio-dia'
        }">
          <div class="neon size-10 flex items-center justify-center">
            <img :src="cycle.icon" alt="" />
          </div>
          <h3 class="font-serif text-2xl text-white">{{ cycle.title }}</h3>
          <p class="text-gray-400">{{ cycle.description }}</p>
          <span class="text-verde-300">{{ cycle.time }}</span>
        </div>
      </div>
    </section>

    <!-- Contato -->
    <section id="contato" class="container mx-auto mb-12 sm:mb-16 grid lg:grid-cols-2 gap-8">
  <div class="grid gap-4">
    <h1 class="font-serif text-4xl text-verde-300 mb-4">Our Contacts</h1>
    <p class="text-gray-200 text-balance mb-8">
      Interested in spending a season at Forest? Contact us by phone or email.
    </p>
    <div>
      <span class="neon h-0.5 w-6 inline-block"></span>
      <h2 class="font-serif text-verde-300 text-2xl mb-2">Base</h2>
      <p class="text-gray-300">Rua da Mata, 123 - Floresta Nacional - RJ</p>
    </div>
    <div>
      <span class="neon h-0.5 w-6 inline-block"></span>
      <h2 class="font-serif text-verde-300 text-2xl mb-2">Email</h2>
      <p class="text-gray-300">contato@forest.com</p>
    </div>
    <div>
      <span class="neon h-0.5 w-6 inline-block"></span>
      <h2 class="font-serif text-verde-300 text-2xl mb-2">Phone</h2>
      <p class="text-gray-300">71 99999-9999</p>
    </div>
  </div>
  <div class="grid gap-4 rounded-xl bg-verde-900 shadow-2xl p-4 lg:p-8">
    <div class="grid gap-1">
      <label class="text-white" for="nome">Name</label>
      <input class="input border-2 border-white rounded focus:outline-none focus:border-verde-400 text-white bg-transparent p-2" type="text" id="nome" name="nome" />
    </div>
    <div class="grid gap-4 sm:grid-cols-2">
      <div class="grid gap-1">
        <label class="text-white" for="email">Email</label>
        <input id="email" name="email" class="input border-2 border-white rounded focus:outline-none focus:border-verde-400 text-white bg-transparent p-2" type="email" />
      </div>
      <div class="grid gap-1">
        <label class="text-white" for="telefone">Phone</label>
        <input id="telefone" name="telefone" class="input border-2 border-white rounded focus:outline-none focus:border-verde-400 text-white bg-transparent p-2" type="text" placeholder="(71) 99999-9999" />
      </div>
    </div>
    <div class="grid gap-1">
      <label class="text-white" for="mensagem">Message</label>
      <textarea id="mensagem" name="mensagem" class="input border-2 border-white rounded focus:outline-none focus:border-verde-400 text-white bg-transparent p-2 resize-none" rows="5"></textarea>
    </div>
    <button class="place-self-start btn">Send Email</button>
  </div>
</section>

    <!-- Parceiros -->
    <section class="container mx-auto mb-12 sm:mb-16">
      <ul class="flex flex-col justify-center items-center py-4 max-sm:divide-y-2 max-sm:divide-verde-900 sm:flex-row sm:gap-8 sm:border-b-2 sm:border-t-2 sm:border-verde-900 sm:py-8">
        <li v-for="partner in partners" :key="partner.alt" class="p-4">
          <img :src="partner.src" :alt="partner.alt" class="max-h-8" />
        </li>
      </ul>
    </section>

    <!-- Footer -->
    <footer class="container mx-auto pb-8">
      <div class="bg-verde-900 grid gap-8 lg:grid-cols-2 mb-8 rounded-2xl p-6 sm:p-12">
        <div class="flex gap-12 max-sm:flex-col max-sm:gap-4">
          <div>
            <h3 class="text-white font-serif text-xl mb-4">Address</h3>
            <p class="text-gray-400">
              Rua da Mata, 123<br />Floresta Nacional<br />Rio de Janeiro, RJ
            </p>
          </div>
          <div>
            <h3 class="text-white font-serif text-xl mb-4">Contact</h3>
            <p class="text-gray-400">
              contato@forest.com<br />+55 71 99999-9999
            </p>
          </div>
        </div>
        <div class="lg:justify-self-end">
          <img class="mb-4" src="/img/forest.svg" alt="Forest Logo" />
          <p class="text-gray-400">Connect with nature</p>
        </div>
      </div>
      <div class="text-gray-400 flex items-center justify-between gap-8 text-sm max-sm:flex-col-reverse">
        <p>© 2024 Forest. All rights reserved.</p>
        <ul class="flex gap-8">
          <li><a class="hover:text-verde-300" href="#">Instagram</a></li>
          <li><a class="hover:text-verde-300" href="#">LinkedIn</a></li>
          <li><a class="hover:text-verde-300" href="#">Facebook</a></li>
        </ul>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const isMenuOpen = ref(false)
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}

const random = Math.floor(Math.random() * 10) + 20
const temperature = ref(`${random}º`)
const weather = ref(random < 25 ? `🌧 ${random + 5}%` : `🌥`)
const day = ref(
  new Date().toLocaleDateString('en-US', { weekday: 'long' })
)
const videoSrc = computed(() => (random < 25 ? '/video/video_chuva.mp4' : '/video/video_sol.mp4'))

const navItems = [
  { text: 'Accommodations', href: '#acomodacoes' },
  { text: 'Events', href: '#eventos' },
  { text: 'Experiences', href: '#experiencias' },
  { text: 'Contact', href: '#contato' },
]

const accommodationItems = [
  'Experience nature up close',
  'Connect with nature',
  'Disconnect from the digital world',
  'Observe wildlife',
  'Choose your favorite cabin',
]

const events = [
  {
    title: 'New Moon',
    day: '23',
    date: 'March 2049',
    month: '03',
    description: 'Best time for stargazing. The sky will be clear and the stars visible.',
    href: '#contato',
  },
  {
    title: 'Meteor Shower',
    day: '15',
    date: 'August 2049',
    month: '08',
    description: 'Best time to observe the meteor shower. The sky will be lit up by stars.',
    href: '#contato',
  },
  {
    title: 'Aurora Borealis',
    day: '15',
    date: 'April 2049',
    month: '04',
    description: 'Best time to observe the Aurora Borealis. The sky will be illuminated by stars.',
    href: '#contato',
  },
]

const experiences = [
  { title: 'Night Observation', description: 'Explore wildlife in its natural habitat under the stars.' },
  { title: 'Wildlife', description: 'Observe wildlife in its natural habitat.' },
  { title: 'Canoeing', description: 'Conquer new horizons with our expert team.' },
]

const experienceImages = [
  { src: '/img/canoagem.jpg', alt: 'Canoagem' },
  { src: '/img/observacao-noturna.jpg', alt: 'Observação Noturna' },
  { src: '/img/vida-selvagem.jpg', alt: 'Vida Selvagem' },
]

const naturalCycle = [
  {
    title: 'Dawn',
    description: 'Wake up to birdsong and join our outdoor walks.',
    time: '05:40 - 07:00',
    icon: '/img/manha.svg',
  },
  {
    title: 'Midday',
    description: 'Explore our shaded trails and enjoy a gourmet picnic in nature.',
    time: '12:00 - 14:00',
    icon: '/img/dia.svg',
  },
  {
    title: 'Night',
    description: 'End your day with our stargazing session.',
    time: '19:00 - 21:00',
    icon: '/img/noite.svg',
  },
]

const partners = [
  { src: '/img/parceiros/caravan.svg', alt: 'Caravan' },
  { src: '/img/parceiros/dogs.svg', alt: 'Dogs' },
  { src: '/img/parceiros/wildbeast.svg', alt: 'Wildbeast' },
  { src: '/img/parceiros/lescone.svg', alt: 'Lescone' },
  { src: '/img/parceiros/surfbot.svg', alt: 'Surfbot' },
]
</script>