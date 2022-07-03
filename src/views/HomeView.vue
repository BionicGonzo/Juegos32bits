<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <br><br>
    <DatosJuegos msg="Tienda de juegos 32 bits"/>
  </div>
</template>

<script>
// @ is an alias to /src
import DatosJuegos from '@/components/DatosJuegos.vue'

export default {
  name: 'HomeView',
  components: {
    DatosJuegos
  }
}
</script>
