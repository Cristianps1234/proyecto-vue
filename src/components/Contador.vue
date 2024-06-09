<script setup>
import { ref } from 'vue';
const contador = ref(0);
const incrementar = () => {
  contador.value++
}
const decrementar = () => {
  contador.value--
}
</script>

<template>
  <h1>Hello world</h1>
  <p>{{ contador }}</p>
  <button @click="incrementar">incrementar</button>
  <button @click="decrementar">decrementar</button>
</template>

<style scoped>
p{
  color:red
}
</style>
