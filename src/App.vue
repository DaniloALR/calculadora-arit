<script setup>
  import { reactive } from 'vue'
  import Cabecalho from './components/Cabecalho.vue'
  import Formulario from './components/Formulario.vue'

  const estado = reactive({
    operacao: '+',
    valorA: 0,
    valorB: 0,
  })

  const fazConta = () => {
    switch(estado.operacao){
      case '+':
        return estado.valorA + estado.valorB
      case '-':
        return estado.valorA - estado.valorB
      case '/':
        return estado.valorA / estado.valorB
      case '*':
        return estado.valorA * estado.valorB
    }
  }
</script>

<template>
    <div class="container">
      <Cabecalho />
      <Formulario :valor-a="evento => estado.valorA = parseInt(evento.target.value)" :valor-b="evento => estado.valorB = parseInt(evento.target.value)" :operacao="evento => estado.operacao = evento.target.value" :faz-conta="fazConta()" />
    </div>
</template>

<style scoped>
</style>
