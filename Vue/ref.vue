<!-- 
En este ejemplo, count es una referencia reactiva.
Es una forma de crear una referencia reactiva para valores primitivos u objetos.
Devuelve un objeto con una propiedad .value que es reactiva.
Ideal para valores únicos y primitivos.

En el template, accedemos al valor de count.value para mostrarlo.
Cuando el botón se presiona, incrementa el valor de count.value.
-->
<template>
    <div>
      <p>{{ count.value }}</p>
      <button @click="increment">Increment</button>
    </div>
  </template>
  
  <script>
  import { ref } from "vue";
  
  export default {
    setup() {
      const count = ref(0);
  
      const increment = () => {
        count.value++;
      };
  
      return { count, increment };
    },
  };
  </script>
