<script setup>
import { computed, ref } from 'vue';

const numero1= ref(0)
const numero2= ref(0)
const operacao = ref('somar')

const total = computed(()=>{

    switch(operacao.value){
        case 'somar':
            return numero1.value + numero2.value;
        case 'subtrair' :
            return numero1.value - numero2.value;
        case 'multiplicar':
            return numero1.value * numero2.value;
        case 'dividir':
            return numero2.value !==0 ? numero1.value / numero2.value : 'erro na divisão'
        default:
            return 0
    }
    
})

</script>

<template>
    <div class="container">
        <h1 class="p-5 ">Calculadora Aritmetica</h1>
        <div class="calculadora" >
            <label class="m-2">Insira o primeiro Valor:  </label>
            <input  type="number"  v-model="numero1"/>
            <label class="m-2" >Insira o segundo Valor: </label>
            <input  type="number" name="" id="" v-model="numero2"/>
            <label class="m-2" >Escolha a Operação: </label> 
            <select v-model="operacao" class="m-2">
              <option value="somar">Somar</option>
              <option  value="subtrair">Subtrair</option>
              <option value="multiplicar">Multiplicar</option>
              <option value="dividir">dividir</option>
            </select>
          
            <p class="m-5 ">Total: {{ total }}</p>
          </div>
       
    </div>
</template>

<style scoped>

</style>
