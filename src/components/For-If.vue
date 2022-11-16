<script setup>
const name = 'Ian Ramirez'
// const styleColor = 'text-decoration:underline'
const isActive = false
const colorsArray = ['green', 'red', 'rebeccapurple']
// const fruitsArray = ["🍎", "🍌", "🍉", "🍓", "🍒"];
// const fruitsArray = [
//   {
//     name: "Manzana",
//     price: "$1.00",
//     description: "Una manzana",
//   },
//   {
//     name: "Pera",
//     price: "$2.00",
//     description: "Una pera",
//   },
//   {
//     name: "Naranja",
//     price: "$3.00",
//     description: "Una naranja",
//   },
// ];
const fruit = {
    name: "Naranja",
    price: "$3.00",
    description: "Una naranja",
};
const newFruitsArray = [
    {
        id: 1,
        name: "Manzana",
        price: "$1.00",
        description: "Una manzana",
        stock: 0,
    },
    {
        id: 2,
        name: "Pera",
        price: "$2.00",
        description: "Una pera",
        stock: 10,
    },
    {
        id: 3,
        name: "Naranja",
        price: "$3.00",
        description: "Una naranja",
        stock: 20,
    },
];
</script>
<template>
    <!-- El template permite crear el HTML -->
    <h1>Hello {{ name }}</h1>
    <h2 :style="`color: ${colorsArray[2]}`"> Texto subrayado</h2>
    <!-- <h2>{{ isActive ? 'Estoy activado' : 'No Estoy activado' }}</h2>  ->Esto es con una ternaria -->
    <!-- <h2 v-if="isActive">Estoy activo</h2>
  <h2 v-if="!isActive">No Estoy activo</h2> -->
    <!-- Practicando los bucles for -->
    <!-- <ul>
    <li v-for="fruit in fruitsArray" key="frut.name">{{ fruit.name }} - {{ fruit.price }} - {{ fruit.description }}
    </li>
  </ul> -->
    <!-- Ahora vamos a recorrer un objeto -->
    <!-- <ul>
    <li v-for="(value, propiedad) in fruit">
      {{ propiedad }} : {{ value }} 
    </li>
  </ul> -->

    <!-- Recorrer el array mediante una condicional -->
    <!-- El condicional siempre va despues del bucle a recorrer -->
    <ul>
        <template v-for="item in newFruitsArray">
            <li v-if="item.stock > 0">{{ item.name }} - {{ item.price }}</li>
        </template>

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