<template>
<h2 class="text-2xl font-semibold mb-2 text-blue-600">Dados Pessoais</h2>
    <form class="w-full max-w-lg">
      <div class="w-full px-3 gap-3 mb-6 md:mb-0 flex">
        <div>
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-first-name">
            Primeiro nome
          </label>
          <input v-model="nome"
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
            id="grid-first-name" type="text" placeholder="Vulgo" />
        </div>
        <div>
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-first-name">
            Sobrenome
          </label>
          <input v-model="sobrenome"
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border- to-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
            id="grid-first-name" type="text" placeholder="Silva" />
        </div>
      </div>

      <div class="w-full  gap-3 px-3 mb-6 md:mb-0 flex">
        <div>
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-first-name">
            Email
          </label>
          <input v-model="email"
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
            id="grid-first-name" type="email" placeholder="ex@gmail.com" />
        </div>
        <div>
          <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-first-name">
            Senha
          </label>
          <input v-model="senha"
            class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
            id="grid-first-name" type="password" placeholder="*****" />
        </div>
      </div>
      <div v-if="isRequired" class="w-full md:w-1/2 px-3 mb-6 md:mb-0">

        <p class="text-red-500 text-xs italic">CAMPOS OBRIGATÓRIO</p>
      </div>


    </form>
    

</template>
