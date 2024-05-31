<!-- En este ejemplo, user es un objeto reactivo. Con reactive, Vue.js crea un objeto proxy reactivo que actúa como un objeto normal, pero sus propiedades son reactivas.
     Así podemos acceder y modificar sus propiedades directamente y Vue.js se encargará de actualizar las vistas donde se utilicen. -->
<template>
    <div>
      <p>{{ user.name }}</p>
      <button @click="changeName">Cambiar nombre</button>
    </div>
  </template>
  
  <script>
  import { reactive } from "vue";
  
  export default {
    setup() {
      const user = reactive({
        name: "John Doe",
      });
  
      const changeName = () => {
        user.name = "Jane Doe"; // Cuando modificamos una propiedad del objeto, Vue.js se encarga de actualizar las vistas donde se utilice esa propiedad
      };
  
      return { user, changeName };
    },
  };
  </script>
