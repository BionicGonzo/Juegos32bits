<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <br>
    <div id="tabla">
      <table class="table table-bordered border-primary">
        <tr>
          <th scope="col">Código</th>
          <th scope="col">Color</th>
          <th scope="col">Nombre</th>
          <th scope="col">Stock</th>
          <th scope="col">Precio</th>
          <th scope="col">Acciones</th>
        </tr>
        <tr v-for="juego in juegos" :key="juego" :style="`color: ${juego.color}`">
          <td>{{juego.codigo}}</td>
          <td>
            <select v-on:change="elegirColor($event, juego.codigo); actionColor(color)">
              <option value=""></option>
              <option value="yellow">Amarillo</option>
              <option value="aqua">Celeste</option>
              <option value="lightgreen">Verde</option>
              <option value="white">Blanco</option>
            </select>
          </td>
          <td>{{juego.nombre}}</td>
          <td>{{juego.stock}}</td>
          <td>{{juego.precio}}</td>
          <td>
            <button @click="masJuegos(juego.codigo)"><i class="fa-solid fa-angle-up"></i></button>
            <button @click="menosJuegos(juego.codigo)"><i class="fa-solid fa-angle-down"></i></button>
          </td>
        </tr>
      </table>
    </div>
    <br><hr>
    <h2>Total: {{totalDeJuegos}}</h2>
  </div>
</template>

<script>
import { mapState, mapGetters, mapMutations, mapActions } from 'vuex'
export default {
  name: 'DatosJuegos',
  props: {
    msg: String
  },
  data() {
    return {
      color: {}
    }
  },
  computed:{
    ...mapState(["juegos", "cantidadDeJuegos"]),
    ...mapGetters(["totalDeJuegos"])
  },
  methods: {
    ...mapMutations([]),
    ...mapActions(["masJuegos", "menosJuegos", "actionColor"]),
    elegirColor(event, codigo) {
      let colorEvento = event.target.value;
      this.color = {"color" : colorEvento, "codigo" : codigo}
      return this.color
    }
  },
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
  width: 70%;
  display: inline-flex;
}

#tabla th {
  color: #FFF;
}

select, button {
  background-color: #FFF;
}

hr {
  width: 70%;
  display: inline-flex;
}
</style>
