<template>
  <form @submit.prevent="guardarDatos">
    <input v-model="nombre" type="text" placeholder="Nombre">
    <input v-model="apellidos" type="text" placeholder="Apellidos">
    <button type="submit">Guardar</button>
  </form>

  <ul>
    <li v-for="(item, index) in listaDatos" :key="index">
      {{ item.nombre }} {{ item.apellidos }}
    </li>
  </ul>
</template>

<script setup>
import { ref } from 'vue'


const nombre = ref('')
const apellidos = ref('')
const listaDatos = ref([])


const guardarDatos = () => {
  if (nombre.value && apellidos.value) {
    listaDatos.value.push({ nombre: nombre.value, apellidos: apellidos.value })
    nombre.value = ''
    apellidos.value = ''
  }
}
</script>

<style scoped>


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




</style>
