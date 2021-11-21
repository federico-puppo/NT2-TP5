<template>
  <div id="app">
    <body>
      <GameManager/>
    </body>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import GameManager from './components/GameManager.vue'
//import Contenedor from "./components/Contenedor.vue";

export default {
  name: "App",
  components: {
    GameManager,
  },
};
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
  /* background: #232323;
  margin: 0;
  font-family: "Montserrat", "Avenir"; */
}
body {
  background: #232323;
  margin: 0;
  font-family: "Montserrat", "Avenir";
}

h1 {
  font-weight: normal;
  line-height: 1.1;
  padding: 20px 0;
}
</style>
