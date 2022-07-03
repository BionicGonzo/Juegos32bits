<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <ul>
      <li v-for="dato in juegos" :key="dato">{{dato.nombre}}</li>
    </ul>
    <div id="tabla">
      <table class="table table-bordered border-primary">
        <tr>
          <th scope="col">Código</th>
          <th scope="col">Nombre</th>
          <th scope="col">Stock</th>
          <th scope="col">Precio</th>
        </tr>
        <tr v-for="registro in juegos" :key="registro" :style="`color: ${registro.color}`">
          <td>{{registro.codigo}}</td>
          <td>{{registro.nombre}}</td>
          <td>{{registro.stock}}</td>
          <td>{{registro.precio}}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'DatosJuegos',
  props: {
    msg: String
  },
  computed:{
    ...mapState(["juegos"]),
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: yellow;
}

#tabla {
  text-align: center;
  width: 50%;
  display: inline-flex;
}

#tabla th {
  color: #FFF;
}
</style>
