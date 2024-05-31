<!-- En este ejemplo, fullName es una propiedad computada que se actualiza automáticamente cuando firstName o lastName cambian.
     Es una forma de simplificar el código y evitar tener que escribir el mismo código repetidamente. Se define como una función que devuelve el valor que queremos mostrar en el template.
     Vue.js se encargará de actualizarla cada vez que se modifican firstName o lastName, para que en el template se muestre el valor actualizado. -->
<template>
    <div>
      <p>Full Name: {{ fullName }}</p>
      <p>Modify first name: <input type="text" v-model="firstName" /></p>
      <p>Modify last name: <input type="text" v-model="lastName" /></p> 
    </div>
  </template>
  
  <script>
  import { ref, computed } from 'vue';
  
  export default {
    setup() {
      const firstName = ref('Jhon');
      const lastName = ref('Doe');
  
      const fullName = computed(() => `${firstName.value} ${lastName.value}`);
  
      return { firstName, lastName, fullName };
    }
  };
  </script>
