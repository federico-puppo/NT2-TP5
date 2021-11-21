<template lang="html">

  <section class="src-components-game-manager">
    <TopHeader ref="topheader"/>
    <Navbar ref="navbar" @setDificult="setDificult"/>
    <Contenedor ref="contenedor" @setTextNavbar="setTextNavbar" @colorDisplay="colorDisplay"/>
  </section>

</template>

<script>

import Navbar from "./Navbar.vue"
import Contenedor from "./Contenedor.vue"
import TopHeader from "./TopHeader.vue"

  export default  {
    name: 'src-components-game-manager',
    props: [],
    components: {
    TopHeader,
    Navbar,
    Contenedor
  },
    mounted () {
      this.init()
      this.restartGame()
    },
    data () {
      return {
      }
    },
    methods: {
      init(){
        this.$refs.topheader.init()
        this.$refs.contenedor.init()
      },
      restartGame(){
        this.$refs.contenedor.restart()
      },
      colorDisplay(pickedColor){
        this.$refs.topheader.rgb=pickedColor
      },
      setTextNavbar(text){
        this.$refs.navbar.message=text
      },
      setDificult(dificultad){
        if (dificultad){
          this.$refs.contenedor.isHard = true
        }else{
          this.$refs.contenedor.isHard = false
        }
        this.restartGame()
      },
      setHeaderStyle(style){
        this.$refs.topheader.style.backgroundColor = style
      },
      compareColors(clickedColor){
        console.log("COLOR CLICKEADO GAME MANAGER"+clickedColor);
      },

    }
}


</script>

<style scoped lang="css">
  .src-components-game-manager {

  }
</style>
