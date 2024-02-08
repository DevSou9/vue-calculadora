<script setup>
import { reactive } from 'vue';
import Header from './components/Header.vue';
import Form from './components/Form.vue';

const estado = reactive({
  resultado: 0,
  numero1: null,
  numero2: null,
  operacao: '+'

})

function soma() {
  if (estado.operacao === '+') {
    estado.resultado = parseFloat(estado.numero1) + parseFloat(estado.numero2);
  }
}

function subtracao() {
  if (estado.operacao === '-') {
    estado.resultado = parseFloat(estado.numero1) - parseFloat(estado.numero2);
  }
}

function multiplicacao() {
  if (estado.operacao === '*') {
    estado.resultado = parseFloat(estado.numero1) * parseFloat(estado.numero2);
  }
}

function divisao() {
  if (estado.operacao === '/') {
    estado.resultado = parseFloat(estado.numero1) / parseFloat(estado.numero2);
  }
}

const calcular = () => {
  console.log(`operacao: ${estado.operacao}`);
  switch (estado.operacao) {
    case '+':
      return soma();

    case '-':
      return subtracao();

    case '*':
      return multiplicacao();

    default:
      return divisao();
  }


}


</script>

<template>
  {{ calcular() }}
  


  <Header :resultado="estado.resultado" :num1="estado.numero1" :num2="estado.numero2"></Header>
 
  <Form :input-num1="e => estado.numero1 = e.target.value" :input-num2="e => estado.numero2 = e.target.value" :select-operacao="e => estado.operacao = e.target.value"></Form>

  
</template>

<style scoped></style>
