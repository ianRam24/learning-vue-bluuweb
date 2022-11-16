<script setup>
const showInConsole = (msg) => { console.log(msg) }
</script>
<template>
    <button @click.left="showInConsole('Left Button')"> Click Me Left</button>
    <button @click.middle="showInConsole('MiddleButton')"> Click Me Middle</button>
    <button @click.right.prevent="showInConsole('Right Button')"> Click Me Right</button>
</template>
<style>
button {
    margin-left: 20px;
}
</style>