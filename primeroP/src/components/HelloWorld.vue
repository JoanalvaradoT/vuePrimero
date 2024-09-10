<template>

  <div>
    <button @click="count++">
      presiona el contador: {{ count }}
    </button>
  </div>

  <form @submit.prevent="sumarNumeros">
    <input type="text" v-model="texto" placeholder="escribe algo">
    <p>{{ texto }}</p> 
    <input type="number" v-model="numero1" placeholder="numero 1">
    <input type="number" v-model="numero2" placeholder="numero 2">
    <button type="submit">Sumar</button>
  </form>

  <div>
    <p>El resultado de la suma es: {{ resultado }}</p>
  </div>
  
</template>

<script setup>
import { ref } from 'vue'


const count = ref(0)
const texto = ref('')
const numero1 = ref(0)
const numero2 = ref(0)


const resultado = ref(0)


const sumarNumeros = () => {
  resultado.value = parseFloat(numero1.value) + parseFloat(numero2.value)
}
</script>

<style scoped>
h1 {
  color: blue;
}

button {
  margin: 10px 10px 10px 0px;
  padding: 8px;
  font-size: 16px;
  width: 200px;
}

form {
  display: flex;
  flex-direction: column;
  gap: 15px; 
  padding-bottom: 20px;
  width: 200px;
}

input {
  padding: 8px;
  font-size: 14px;
}

p {
  font-size: 14px;
  color: grey;
  margin: 0;
}
</style>
