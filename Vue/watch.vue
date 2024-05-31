<!-- En este ejemplo, el watcher observa los cambios en count y actualiza previousCount con el valor anterior de count cada vez que cambia.
     El watcher es una forma de reaccionar a cambios en una referencia reactiva.
     Tiene dos parámetros: la referencia reactiva que queremos observar y una función que se ejecutará cada vez que cambie esa referencia.
     Esta función recibe dos parámetros: el nuevo valor de la referencia y el valor anterior.
     En este caso, cada vez que cambie count, la función guardará el valor anterior en previousCount. -->
<template>
    <div>
      <p>Count: {{ count }}</p>
      <p>Previous Count: {{ previousCount }}</p>
      <button @click="increment">Increment</button>
    </div>
  </template>
  
  <script>
  import { ref, watch } from 'vue';
  
  export default {
    setup() {
      const count = ref(0);
      const previousCount = ref(0);
  
      const increment = () => {
        count.value++;
      };
  
      watch(count, (newVal, oldVal) => {
        previousCount.value = oldVal;
      });
  
      return { count, previousCount, increment };
    }
  };
  </script>
  </script>
