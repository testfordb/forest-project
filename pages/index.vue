<template>
  <div class="bg-verde-800 font-sans text-white scroll-smooth">
    <WeatherInfo />
    <Header />
    <main class="container mx-auto">
      <Hero />
      <Accommodations />
      <Events />
      <Experiences />
      <NaturalCycle />
      <ContactForm />
      <Partners />
    </main>
    <Footer />
  </div>
</template>

<script setup lang="ts">
import WeatherInfo from '~/components/WeatherInfo.vue'
import Header from '~/components/Header.vue'
import Hero from '~/components/Hero.vue'
import Accommodations from '~/components/Accommodations.vue'
import Events from '~/components/Events.vue'
import Experiences from '~/components/Experiences.vue'
import NaturalCycle from '~/components/NaturalCycle.vue'
import ContactForm from '~/components/ContactForm.vue'
import Partners from '~/components/Partners.vue'
import Footer from '~/components/Footer.vue'
</script>
