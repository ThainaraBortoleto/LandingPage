<script setup>
import { ref, computed } from 'vue'
import tab1 from "./FormSigin/tab1.vue"
import tab2 from './FormSigin/tab2.vue';
import tab3 from "./FormSigin/tab3.vue"

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
const sobrenome = ref('')
const email = ref('')
const senha = ref('')
const isRequired = ref(false)
const cep = ref('')
const cidade = ref('')
const estado = ref('')
const endereco = ref('')
function cadastro() {
  alert("Cadastro feito")
  if (nome.value != "" && sobrenome.value != "" && email.value != "" && senha.value != "") {
    isRequired.value = false
    console.log(isRequired.value)
  } else {
    isRequired.value = true
  }
}
</script>
<template>
  <!-- component -->
  <div v-data="{ activeTab: 1 }" class="p-8">
    <div class="mx-auto">
      <div class="mb-4 flex space-x-4 p-2 bg-white rounded-lg shadow-md">
        <button @click="activeTab = 1" :class="{ 'bg-blue-600 text-white': activeTab === 1 }"
          class="flex-1 py-2 px-4 rounded-md focus:outline-none focus:shadow-outline-blue transition-all duration-300">
          Sessão 1
        </button>
        <button @click="activeTab = 2" :class="{ 'bg-blue-600 text-white': activeTab === 2 }"
          class="flex-1 py-2 px-4 rounded-md focus:outline-none focus:shadow-outline-blue transition-all duration-300">
          Section 2
        </button>
        <button @click="activeTab = 3" :class="{ 'bg-blue-600 text-white': activeTab === 3 }"
          class="flex-1 py-2 px-4 rounded-md focus:outline-none focus:shadow-outline-blue transition-all duration-300">
          Section 3
        </button>
      </div>
    </div>
    <div v-show="activeTab === 1"
      class="transition-all duration-300 bg-white p-4 rounded-lg shadow-md border-l-4 border-blue-600">
      <tab1 />
    </div>

    <div v-show="activeTab === 2"
      class="transition-all duration-300 bg-white p-4 rounded-lg shadow-md border-l-4 border-blue-600">
      <tab2 />


    </div>






    <div v-show="activeTab === 3"
      class="transition-all duration-300 bg-white p-4 rounded-lg shadow-md border-l-4 border-blue-600">
      <tab3 @concluir="cadastro"/>
    </div>
  </div>

</template>
