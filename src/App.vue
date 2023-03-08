<template>
<h2>Cena{{ contador + 1 }}</h2>

</template>

<script setup>
  import {ref} from "vue"
  import{productos} from "./datos.js"
  const contador=ref(0)
</script>

<style scoped>

</style>
