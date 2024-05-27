<script setup>
import { ref } from 'vue'
defineEmits(["concluir"]) 
const option = ref(1)
function setOption(){
console.log(option.value)
}
</script>
<template>
<h2 class="text-2xl font-semibold mb-2 text-blue-600">Formas de pagamento</h2>
      <p class="text-gray-700">
        Aqui você coloca suas formas de pagamento para aumentar seus conhecimentos!
      </p>
      <div>
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2" for="grid-first-name">
          Formas de pagamento 
        </label> 
        <select @change="setOption" v-model="option" class="mb-3 block w-full px-4 py-2 mt-2 text-gray-700 bg-white border border-gray-300 rounded-md focus:outline-none focus:border-indigo-500">
  <option value="1">Cartão de crédito</option>
  <option value="2">Débito automático</option>
</select> 
</div>

   <div v-if="option==1">    
    <div>
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2">Número do cartão</label>
        <input  class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"/>
    </div>
    <div>
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2">CVV</label>
        <input  class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"/>
    </div> 
    <div>
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2">Validade</label>
        <input  class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"/>
    </div> 
    <div>
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2">CPF</label>
        <input  class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"/>
    </div> 

</div>    
<div v-if="option==2">    
    <div>
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2">Banco</label>
        <input  class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"/>
    </div>
    <div>
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2">Número da conta</label>
        <input  class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"/>
    </div>
    <div>
        <label class="block uppercase tracking-wide text-gray-700 text-xs font-bold mb-2">Número da agência</label>
        <input  class="appearance-none block w-full bg-gray-200 text-gray-700 border border-black-500 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white"/>
    </div>
    <div class="flex"> 
        <input type="checkbox" class="mr-6" /> 
        <label class="block uppercase tracking-wide text-gray-700 text-sm wrap font-bold mb-2">Aceito os termos do contrato com juros no atraso do pagamento</label>
        
    </div> 
    <button class="mt-5 bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded"
      @click="$emit("concluir")">enviar</button> 
</div>  

    
</template>