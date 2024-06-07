<script setup>

import { reactive } from 'vue';
import Header from './components/Header.vue';
import Form from './components/Form.vue';
import Footer from './components/Footer.vue';

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
