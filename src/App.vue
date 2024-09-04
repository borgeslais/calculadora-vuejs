<script setup>
import Calculadora from './components/Calculadora.vue';
</script>

<template>
  <div class="container">
    <h1>Calculadora Aritmética VueJs</h1>
    <Calculadora />
  </div>

</template>

<style scoped>
.container {
  max-width: 40vw;
  margin: 10% auto;
  padding: 20px;
  background-color: #271c57;
  border-radius: 16px;
}

h1 {
  color: #efefef;
  text-align: center;
}
</style>
