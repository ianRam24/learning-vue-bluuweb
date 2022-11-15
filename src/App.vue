<script setup>
const name = 'Ian Ramirez'
// const styleColor = 'text-decoration:underline'
const isActive = false
const colorsArray = ['green', 'red', 'rebeccapurple']
// const fruitsArray = ["🍎", "🍌", "🍉", "🍓", "🍒"];
const fruitsArray = [
  {
    name: "Manzana",
    price: "$1.00",
    description: "Una manzana",
  },
  {
    name: "Pera",
    price: "$2.00",
    description: "Una pera",
  },
  {
    name: "Naranja",
    price: "$3.00",
    description: "Una naranja",
  },
];
const fruit = {
  name: "Naranja",
  price: "$3.00",
  description: "Una naranja",
};
</script>
<template>
  <!-- El template permite crear el HTML -->
  <h1>Hello {{ name }}</h1>
  <h2 :style="`color: ${colorsArray[2]}`"> Texto subrayado</h2>
  <!-- <h2>{{ isActive ? 'Estoy activado' : 'No Estoy activado' }}</h2>  ->Esto es con una ternaria -->
  <h2 v-if="isActive">Estoy activo</h2>
  <h2 v-if="!isActive">No Estoy activo</h2>
  <!-- Practicando los bucles for -->
  <ul>
    <li v-for="fruit in fruitsArray" key="frut.name">{{ fruit.name }} - {{ fruit.price }} - {{ fruit.description }}
    </li>
  </ul>
  <!-- Ahora vamos a recorrer un objeto -->
  <ul>
    <li v-for="(value, propiedad) in fruit">
      {{ propiedad }} : {{ value }}
    </li>
  </ul>


</template>
<style>
ul {
  list-style: none;
}

h1 {
  color: #169b7e;
}
</style>

<!-- Se pueden eliminar las etiquetas script y style template es obligatorio  -->
<!-- El v-bind permite la comuncación entre el JS y el css de un archivo -->