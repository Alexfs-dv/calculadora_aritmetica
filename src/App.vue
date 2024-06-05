<script setup>
import { reactive } from 'vue';
import Header from './components/Header.vue';
import Form from './components/Form.vue';
import Footer from './components/Footer.vue';

const estado = reactive({
  operacao: ''
})

const soma = () => {
  return numberA + numberB
}

const subtracao = () => {
  return numberA - numberB 
}

const multiplicacao = () => {
  return numberA * numberB 
}

const divisao = () => {
  return numberA / numberB
}

const operacaoSelecionada = () => {
  const { operacao } = estado;

  switch(operacao){
    case 'soma':
      return soma();
    case 'subtracao':
      return subtracao();
    case 'multiplicacao':
      return multiplicacao();
    case 'divisao':
      return divisao();   
  }
}
console.log(operacaoSelecionada)
</script>

<template>
  <Header />
  <Form :operacao-selecionada="evento => estado.operacao = evento.target.value" />
  <Footer />
</template>

<style>
  body {
    background: linear-gradient(rgba(0,0,0, .85), rgba(0,0,0, .85)), url('/img/bgimage.png');
    background-size: auto;
  }
</style>
