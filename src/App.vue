<!-- <template>
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
Minuto 01:05 falla imagenes -->


<template>
  <h2>Cena {{ contador + 1 }}
    con el rey godo {{ rey }}
  </h2>
  <img @:src="imagen" alt="">
  <button @:click="siguiente">Siguiente ({{ contador + 1 }}/ {{ total }})</button>
</template>

<script setup>
import { ref, computed } from "vue"
import { productos } from "./datos.js"

// Initialize reactive variable contador with starting value of 0
const contador = ref(0)

// Initialize reactive variable total with the number of products
const total = productos.length;

// Define the URL for the images
const ruta = "https://www.html6.es/img/rey_"

// Function to increment the counter and cycle back to 0 if it exceeds the number of products
const siguiente = () => {
  // Increment the value of contador
  contador.value++
  // Check if contador is greater than or equal to total
  if (contador.value >= total) {
    // If so, reset contador back to 0
    contador.value = 0;
  }
}

// Computed property to get the name of the product and format it to have the first letter capitalized
const rey = computed(() => {
  // Get the name of the product
  const elNombre = productos[contador.value].nombre.toLowerCase()
  // Capitalize the first letter and return the formatted name
  return elNombre.substring(0, 1).toUpperCase() + elNombre.substring(1)
})

// Computed property to get the URL for the image
const imagen = computed(() => {
  // Use template literals to dynamically construct the URL using the value of contador and ruta
  return `${ruta}${productos[contador.value].nombre.toLowerCase()}.png`
})

</script>

<style scoped></style>
