<script setup>
import { ref, computed } from 'vue'

let counter = ref(0)
const increment = () => { counter.value++ }
const decrement = () => {
  counter.value--
}
const reset = () => { counter.value = 0 }

const classCounter = computed(() => {
  if (counter.value === 0) {
    return "zero";
  }
  if (counter.value <= 0) {
    return "negative";
  }
  if (counter.value >= 0) {
    return "positive";
  }
})

const favouriteList = ref([])
const add = () => {
  let currentNumber = counter.value
  favouriteList.value.push(currentNumber)
}
const blockButton = computed(() => {
  const repetedNumber = favouriteList.value.find(number => number === counter.value)
  return repetedNumber || repetedNumber === 0
})

</script>
<template>
  <p :class="classCounter">{{ counter }}</p>
  <button @click="increment">Increment</button>
  <button @click="decrement">Decrement</button>
  <button @click="reset">Reset</button>
  <button @click="add" :disabled="blockButton">Add Favourite</button>
  <ul>
    <li v-for="(number, idx) in favouriteList" :key="idx">{{ number }}</li>
  </ul>

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

.zero {
  color: whitesmoke;
}

ul {
  list-style: none;
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
<!-- El computed siempre tiene que retornar algo -->
<!-- Computed nos permite cambiar las clases mediante una condicional -->
<!-- Cuando se trabaja con datos reactivos se recomienda usar el computed -->
<!-- Crear un boton que agreue el elmentoi deseado a un array -->