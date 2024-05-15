<script setup>
import { ref, computed } from 'vue'

// const tabs = [
//   {
//     title: 'Dados Pessoais',
//     id: 1
//   },
//   {
//     title: 'Cursos',
//     id: 2
//   }
// ]

const activeTab = ref(1)
const nome = ref('')
const sobrenome =ref ('')
const  email = ref('') 
const  senha= ref('')
const isRequired = ref(false)
const cep = ref ('')
const cidade = ref ('')
const estado = ref ('') 
const endereco = ref ('')
function cadastro () { 
  if (nome.value != "" && sobrenome.value != "" && email.value != "" && senha.value != ""){
    isRequired.value=false
    console.log(isRequired.value)
  }else {
    isRequired.value=true
  }
}
</script>
<template>
  <!-- component -->
  <div v-data="{ activeTab: 1 }" class="p-8">
    <div class="mx-auto">
      <div class="mb-4 flex space-x-4 p-2 bg-white rounded-lg shadow-md">
        <button
          @click="activeTab = 1"
          :class="{ 'bg-blue-600 text-white': activeTab === 1 }"
          class="flex-1 py-2 px-4 rounded-md focus:outline-none focus:shadow-outline-blue transition-all duration-300"
        >
          Sessão 1
        </button>
        <button
          @click="activeTab = 2"
          :class="{ 'bg-blue-600 text-white': activeTab === 2 }"
          class="flex-1 py-2 px-4 rounded-md focus:outline-none focus:shadow-outline-blue transition-all duration-300"
        >
          Section 2
        </button>
        <button
          @click="activeTab = 3"
          :class="{ 'bg-blue-600 text-white': activeTab === 3 }"
          class="flex-1 py-2 px-4 rounded-md focus:outline-none focus:shadow-outline-blue transition-all duration-300"
        >
          Section 3
        </button>
      </div>

      <div
        v-show="activeTab === 1"
        class="transition-all duration-300 bg-white p-4 rounded-lg shadow-md border-l-4 border-blue-600"
      >
        <h2 class="text-2xl font-semibold mb-2 text-blue-600">Dados Pessoais</h2>
        <form class="w-full max-w-lg">
          <div class="w-full px-3 gap-3 mb-6 md:mb-0 flex">
            <div>
              <label
                class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                for="grid-first-name"
              >
                Primeiro nome
              </label>
              <input v-model="nome"
                class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
                id="grid-first-name"
                type="text"
                placeholder="Vulgo"
              />
            </div>
            <div>
              <label
                class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
                for="grid-first-name"
              >
                Sobrenome
              </label>
              <input
              v-model="sobrenome"
                class="appearance-none block w-full bg-gray-200 text-gray-700 border border- to-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
                id="grid-first-name"
                type="text"
                placeholder="Silva"
              />
            </div>
          </div>
          
          <div class="w-full  gap-3 px-3 mb-6 md:mb-0 flex">
          <div>
            <label
              class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
              for="grid-first-name"
            >
              Email
            </label>
            <input 
            v-model="email"
              class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
              id="grid-first-name"
              type="email"
              placeholder="ex@gmail.com"
            />
          </div>
            <div>
              <label
              class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
              for="grid-first-name"
            >
              Senha
            </label>
            <input
            v-model="senha"
              class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
              id="grid-first-name"
              type="password"
              placeholder="*****"
            />
            </div>
          </div> 
          <div v-if="isRequired" class="w-full md:w-1/2 px-3 mb-6 md:mb-0">
           
           <p class="text-red-500 text-xs italic">CAMPOS OBRIGATÓRIO</p>
         </div>
          
         
        </form>
        <button class="mt-5 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" @click="cadastro">enviar</button>
      </div>

      <div
        v-show="activeTab === 2"
        class="transition-all duration-300 bg-white p-4 rounded-lg shadow-md border-l-4 border-blue-600"
      >
       
         
        <div>
              <label
              class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
              for="grid-first-name"
            >
              Endereço
            </label>
            <input
            v-model="endereco"
              class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
              id="grid-first-name"
              type="text"
              placeholder="Rua das Colves n 08"
            />
            </div>
            <div>
              <label
              class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
              for="grid-first-name"
            >
              CEP
            </label>
            <input
            v-model="cep"
              class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
              id="grid-first-name"
              type="text"
              placeholder="04569-070"
            />
            </div>
            <div>
              <label
              class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
              for="grid-first-name"
            >
             Cidade
            </label>
            <input
            v-model="cidade"
              class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
              id="grid-first-name"
              type="text"
              placeholder="São Paulo"
            />
            </div>
            <div>
              <label
              class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2"
              for="grid-first-name"
            >
             Estado
            </label>
            <input
            v-model="estado"
              class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"
              id="grid-first-name"
              type="text"
              placeholder="São Paulo"
            />
            </div>
            </div>
            
      </div>
  
     
     

      <div
        v-show="activeTab === 3"
        class="transition-all duration-300 bg-white p-4 rounded-lg shadow-md border-l-4 border-blue-600"
      >
        <h2 class="text-2xl font-semibold mb-2 text-blue-600">Section 3 Content</h2>
        <p class="text-gray-700">
          Fusce hendrerit urna vel tortor luctus, nec tristique odio tincidunt. Vestibulum ante
          ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae.
        </p>
      </div>
    </div>
  
</template>
