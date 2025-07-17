<template>
  <section
    id="contato"
    class="container mx-auto mb-12 sm:mb-16 grid lg:grid-cols-2 gap-8"
  >
    <div class="grid gap-4">
      <h1 class="font-serif text-4xl text-verde-300 mb-4">
        Our Contacts
      </h1>
      <p class="text-gray-200 text-balance mb-8">
        Interested in spending a season at Forest? Contact us by phone
        or email.
      </p>
      <div>
        <span class="neon h-0.5 w-6 inline-block"></span>
        <h2 class="font-serif text-verde-300 text-2xl mb-2">
          Base
        </h2>
        <p class="text-gray-300">
          Rua da Mata, 123 - Floresta Nacional - RJ
        </p>
      </div>
      <div>
        <span class="neon h-0.5 w-6 inline-block"></span>
        <h2 class="font-serif text-verde-300 text-2xl mb-2">
          Email
        </h2>
        <p class="text-gray-300">contato@forest.com</p>
      </div>
      <div>
        <span class="neon h-0.5 w-6 inline-block"></span>
        <h2 class="font-serif text-verde-300 text-2xl mb-2">
          Phone
        </h2>
        <p class="text-gray-300">71 99999-9999</p>
      </div>
    </div>
    <div
      class="grid gap-4 rounded-xl bg-verde-900 shadow-2xl p-4 lg:p-8"
    >
      <div class="grid gap-1">
        <label class="text-white" for="nome">Name</label>
        <input
          class="input border-2 border-white rounded focus:outline-none focus:border-verde-400 text-white bg-transparent p-2"
          type="text"
          id="nome"
          name="nome"
        />
      </div>
      <div class="grid gap-4 sm:grid-cols-2">
        <div class="grid gap-1">
          <label class="text-white" for="email">Email</label>
          <input
            id="email"
            name="email"
            class="input border-2 border-white rounded focus:outline-none focus:border-verde-400 text-white bg-transparent p-2"
            type="email"
          />
        </div>
        <div class="grid gap-1">
          <label class="text-white" for="telefone">Phone</label>
          <input
            id="telefone"
            name="telefone"
            class="input border-2 border-white rounded focus:outline-none focus:border-verde-400 text-white bg-transparent p-2"
            type="text"
            placeholder="(71) 99999-9999"
          />
        </div>
      </div>
      <div class="grid gap-1">
        <label class="text-white" for="mensagem">Message</label>
        <textarea
          id="mensagem"
          name="mensagem"
          class="input border-2 border-white rounded focus:outline-none focus:border-verde-400 text-white bg-transparent p-2 resize-none"
          rows="5"
        ></textarea>
      </div>
      <button class="place-self-start btn">Send Email</button>
    </div>
  </section>
</template>
