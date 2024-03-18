<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue'
import Operacao from './components/Operacao.vue'
import Resultado from './components/Resultado.vue'

  const estado = reactive({
    operation: '+',
    num1: '',
    num2:''
  })

const resultado = () => {
  const {operation} = estado
  switch (operation) {
    case '-':
      return parseFloat(estado.num1) - parseFloat(estado.num2); //parseFloat para transofrmar em número
      case '*':
      return parseFloat(estado.num1) * parseFloat(estado.num2);
      case '/':
      return parseFloat(estado.num1) / parseFloat(estado.num2);
      default:
      return parseFloat(estado.num1) + parseFloat(estado.num2);
  }
}
</script>
<template>
  <body>
    <div class="container">
      <Cabecalho></Cabecalho>
      <Operacao :operacao="evento=> estado.operation = evento.target.value" :num1="evento => estado.num1 = evento.target.value" :num2="evento => estado.num2 = evento.target.value">  </Operacao>
      <Resultado :num1="estado.num1" :num2="estado.num2" :resultado="resultado()"></Resultado>
    </div>
  </body>
</template>

<style scoped>
*{
  margin: 0;
  padding: 0;
}

.container {
  width: 900px;
  margin: 50px auto;
  text-align: center;
  background-color: rgb(205, 205, 206);
  color: #434242;
  border-radius: 8px;
  border:solid 1px #434242;
}
</style>