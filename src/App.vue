<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Calculadora from './components/Calculadora.vue';
import Resultado from './components/Resultado.vue';

const state = reactive({
  filtro: 'soma',
  num1: '',
  num2: '',
  resultado: '',
})

const soma = () => {
  const resultadoSoma = state.num1 + state.num2
  state.resultado = resultadoSoma;
  return state.resultado
}

const subtracao = () => {
  const resultadoSubtracao = state.num1 - state.num2
  state.resultado = resultadoSubtracao;
  return state.resultado
}

const multiplicacao = () => {
  const resultadoMultiplicacao = state.num1 * state.num2
  state.resultado = resultadoMultiplicacao;
  return state.resultado
}

const divisao = () => {
  const resultadoDivisao = state.num1 / state.num2
  state.resultado = resultadoDivisao
  return state.resultado
}
</script>


<template>
  <div class="container">
    <div class="background-calculator">
      <Cabecalho />
      <Calculadora :primeiro-numero="event => state.num1 = Number(event.target.value)" :segundo-numero="event => state.num2 = Number(event.target.value)" :filtro="state.filtro" :selecionar-filtro="event => state.filtro = event.target.value"/>
      <Resultado :filtro="state.filtro" :funcao-soma="soma()" :funcao-sub="subtracao()" :funcao-mult="multiplicacao()" :funcao-div="divisao()"/>
    </div>
  </div>
</template>

<style scoped></style>
