<template>
<h2>Cena{{ contador + 1 }}</h2>
<button @:click="siguiente">Siguiente ({{ contador +1 }}/ {{total}})</button>
</template>

<script setup>
  import {ref} from "vue"
  import{productos} from "./datos.js"
  const contador=ref(0)
  const total=productos.length;
  const siguiente=()=>{
    contador.value++
    if (contador.value>=total){
      contador.value=0;
    }
  }
</script>

<style scoped>

</style>
<!-- Minuto 55:14 -->