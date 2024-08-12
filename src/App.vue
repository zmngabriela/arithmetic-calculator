<script setup>
  import { reactive } from 'vue';
  import Inputs from './components/Inputs.vue';
  import Actions from './components/Actions.vue';

  const state = reactive({
    num1: 0,
    num2: 0,
    operator: '',
    result: 0,
    isCalculated: false,
  })

  const calculation = () => {
    state.isCalculated = true;

    switch (state.operator) {
      case 'somar':
        state.result = Number(state.num1) + Number(state.num2);
        break;
      case 'subtrair':
        state.result = Number(state.num1) - Number(state.num2);
        break;
      case 'dividir':
        state.result = Number(state.num1) / Number(state.num2);
        break;
      case 'multiplicar':
        state.result = Number(state.num1) * Number(state.num2);
        break;
      default:
        state.result = 'Operação inválida'
    }
  }

  const setOperator = (evento) => {
    state.operator = evento.target.value;
    calculation();
  }

  const restart = () => {
    state.num1 = 0;
    state.num2 = 0;
    state.operator = '';
    state.result = 0;
    state.isCalculated = false;
  }
</script>

<template>
  <div class="container centered">
    <h2 :class="{ hidden: !state.isCalculated }">O resultado do cálculo é: {{ state.result }}</h2>
    <Inputs :isCalculated="state.isCalculated" :result="state.result" :getNum1="evento => state.num1 = evento.target.value" :getNum2="evento => state.num2 = evento.target.value" :num1="state.num1" :num2="state.num2"></Inputs>
    <Actions :setOperator="setOperator" :restart="restart"></Actions>
  </div>
</template>

<style scoped>
  .hidden {
    visibility: hidden;
  }
</style>

<style>
  body {
    width: 100vw;
    height: 100vh;
    margin: 0;
    padding: 0;
    background-color: black;
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
  }
</style>