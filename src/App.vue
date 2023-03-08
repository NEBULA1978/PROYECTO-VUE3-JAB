<template>
<h2>Cena {{ contador + 1 }}
  con el rey godo {{ rey }}
</h2>
<img @:src="imagen" alt="">
<button @:click="siguiente">Siguiente ({{ contador +1 }}/ {{total}})</button>
</template>

<script setup>
  import {ref,computed} from "vue"
  import{productos} from "./datos.js"
  const contador=ref(0)
  const total=productos.length;
  const ruta="https://www.html6.es/img/rey_"
  const siguiente=()=>{
    contador.value++
    if (contador.value>=total){
      contador.value=0;
    }
  }
  const rey=computed(()=>{
    const elNombre=productos[contador.value].nombre.toLowerCase()
    return  elNombre.substring(0, 1).toUpperCase() + elNombre.substring(1)
  })
const imagen=computed(()=>{
  
  // return ruta+productos[contador.value].nombre.toLowerCase()+".png"
  return `${ruta}${productos[contador.value].nombre.toLowerCase()}.png`
})   

</script>

<style scoped>

</style>
<!-- Minuto 01:05 falla imagenes-->