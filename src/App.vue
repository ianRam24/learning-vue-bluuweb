<script setup>
import { ref } from 'vue'

let counter = ref(0)
const increment = () => { counter.value++ }
const decrement = () => {
  counter.value--
}
const reset = () => { counter.value = 0 }


</script>
<template>
  <p :class="counter <= 0 ? 'negative' : 'positive'">{{ counter }}</p>
  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>
  <button @click="reset">Reset</button>
</template>
<style>
button {
  margin-left: 20px;
}

.positive {
  color: green;
}

.negative {
  color: red;
}
</style>

<!-- Se pueden eliminar las etiquetas script y style template es obligatorio  -->
<!-- El v-bind permite la comuncación entre el JS y el css de un archivo -->
<!-- En vue no importa el v-for-of o el v-for-in -->
<!-- Se pueden terner 2 o mas etiquetas template en un archivo Vue -->
<!-- La segunda etiquta template viene siendo como el fragment en react -->
<!-- Para prevenir un evento por defecto es con un prevent del evento a prevenir  -->
<!-- En vue se ovupa el ref para mantener la valor original -->
<!-- Al agregarle el ref a la varibale original lo estamios colocando como variable reactiva  -->