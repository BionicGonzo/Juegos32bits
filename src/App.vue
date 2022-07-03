<template>
  <div id="app">
    <nav>
      <router-link to="/">Inicio</router-link> |
      <router-link to="/about">Acerca de</router-link>
    </nav>
    <router-view></router-view>
  </div>
</template>

<style>
body {
  background-color: #000
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #FFF;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #FFF;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: yellow;
}

nav a:hover {
  color: yellow;
}
</style>
