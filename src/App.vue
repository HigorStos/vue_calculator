<script setup>
  import { reactive } from 'vue';
  import Header from './components/Header.vue';
  import Form from './components/Form.vue';
  import Result from './components/Result.vue';

  const estado = reactive({
    numA: 0,
    numB: 0,
    resultado: 0,
    operacao: '',
  })

  const adicao = () => {
    return estado.resultado = Number(estado.numA) + Number(estado.numB);
  }

  const subtracao = () => {
    return estado.resultado = Number(estado.numA) - Number(estado.numB);
  }

  const multiplicacao = () => {
    return estado.resultado = Number(estado.numA) * Number(estado.numB);
  }

  const divisao = () => {
    return estado.resultado = Number(estado.numA) / Number(estado.numB);
  }

  const getResultado = () => {
    const { operacao } = estado;

    switch(operacao) {
      case 'subtracao':
        return subtracao();
      case 'multiplicacao':
        return multiplicacao();
      case 'divisao':
        return divisao();
      default:
        return adicao();
    }
  }
</script>

<template>
  <div class="container w-25">
    <Header />
    <Form :num-a="evento => estado.numA = evento.target.value" 
      :num-b="evento => estado.numB = evento.target.value" 
      :operation="evento => estado.operacao = evento.target.value" />
    <Result :resultado="getResultado()" />
  </div>
</template>

<style scoped>
</style>
