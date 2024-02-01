<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const acao = reactive({
  operador: '',
  valor1: '',
  valor2: '',
});

const calculaResultado = () => {
  switch (acao.operador) {
    case 'somar':
      return Number(acao.valor1) + Number(acao.valor2);
    case 'subtrair':
      return Number(acao.valor1) - Number(acao.valor2);
    case 'multiplicar':
      return Number(acao.valor1) * Number(acao.valor2);
    case 'dividir':
      return Number(acao.valor1) / Number(acao.valor2);
    default:
      return 0;
  }
};
</script>

<template>
  <div class="container text-center bg-light rounded py-5">
    <Cabecalho />
    <Formulario :operacao = "acao"/>
    <Resultado :resultado = "calculaResultado()" />
  </div>
</template>

<style scoped>
  .container {
    margin-top: 50px;
    max-width: 800px;
    padding:0 20px ;    
  }
</style>
