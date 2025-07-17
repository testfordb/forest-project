<template>
  <footer class="container mx-auto pb-8">
    <div
      class="bg-verde-900 grid gap-8 lg:grid-cols-2 mb-8 rounded-2xl p-6 sm:p-12"
    >
      <div class="flex gap-12 max-sm:flex-col max-sm:gap-4">
        <div>
          <h3 class="text-white font-serif text-xl mb-4">
            Address
          </h3>
          <p class="text-gray-400">
            Rua da Mata, 123<br />Floresta Nacional<br />Rio de Janeiro,
            RJ
          </p>
        </div>
        <div>
          <h3 class="text-white font-serif text-xl mb-4">
            Contact
          </h3>
          <p class="text-gray-400">
            contato@forest.com<br />+55 71 99999-9999
          </p>
        </div>
      </div>
      <div class="lg:justify-self-end">
        <img
          class="mb-4"
          src="/img/forest.svg"
          alt="Forest Logo"
        />
        <p class="text-gray-400">Connect with nature</p>
      </div>
    </div>
    <div
      class="text-gray-400 flex items-center justify-between gap-8 text-sm max-sm:flex-col-reverse"
    >
      <p>© 2024 Forest. All rights reserved.</p>
      <ul class="flex gap-8">
        <li>
          <a class="hover:text-verde-300" href="#">Instagram</a>
        </li>
        <li>
          <a class="hover:text-verde-300" href="#">LinkedIn</a>
        </li>
        <li>
          <a class="hover:text-verde-300" href="#">Facebook</a>
        </li>
      </ul>
    </div>
  </footer>
</template>
