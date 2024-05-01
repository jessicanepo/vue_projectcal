<script setup>
import { ref } from 'vue';

const num1 = ref(0);
const num2 = ref(0);
const operator = ref('+');
const result = ref(0);

const calculate = () => {
  switch (operator.value) {
    case '+':
      result.value = parseFloat(num1.value) + parseFloat(num2.value);
      break;
    case '-':
      result.value = parseFloat(num1.value) - parseFloat(num2.value);
      break;
    case '*':
      result.value = parseFloat(num1.value) * parseFloat(num2.value);
      break;
    case '/':
      result.value = parseFloat(num1.value) / parseFloat(num2.value);
      break;
    default:
      result.value = 0;
  }
};
</script>

<template>
  <div id="app">
    <input type="number" v-model="num1" @input="calculate">
    <select v-model="operator" @change="calculate">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
    </select>
    <input type="number" v-model="num2" @input="calculate">
    <p>Resultado: {{ result }}</p>
  </div>
</template>

<style scoped>
#app {
  text-align: center;
  margin-top: 50px;
}

input[type="number"] {
  width: 100px;
  margin: 0 10px;
  padding: 5px;
}

select {
  padding: 5px;
}
</style>
