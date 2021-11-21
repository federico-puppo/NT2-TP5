<template lang="html">
  <section class="src-components-contenedor">
    <div ref="container">
      <Color @getColor="getColor"/>
      </div>
  </section>
</template>

<script lang="js">
import Color from "./Color.vue"
import Vue from "vue"

  export default  {
    name: 'src-components-contenedor',
    props: [],
    components:{
      Color
      },
    data () {
      return {
        squares: [],
        colors:[],
        colorCount:'',
        isHard: '',
        pickedColor:'',
        
      }
    },
    methods: {
      init(){
        this.restart()
        },
      crearSquares(){
        for (let i = 0; i <this.colorCount; i++) {
          let comp = Vue.extend(Color)
          let instance = new comp()
          instance.$mount()
          this.$refs.container.appendChild(instance.$el)
          this.squares.push(instance)
          this.squares[i].setColor(this.colors[i])
        }
        },
      destruirSquares(){
          this.squares = []
          while (this.$refs.container.hasChildNodes()) {
            this.$refs.container.removeChild(this.$refs.container.firstChild)
            }
          this.colors = []
        },
      getColor(){
        console.log("COLOR CLICKEADO EN CONTAINER")
        //this.$emit('compareColors')
        // if (clickedColor === this.pickedColor) {
        // //messageDisplay.textContent = "You Picked Right!";
        // this.$emit("setTextNavbar","You Picked Right!")
        // this.setAllColorsTo(this.pickedColor);
        // //restartButton.textContent = "Play Again!";
        // this.$emit("setGameActive",false)
        // //header.style.backgroundColor = pickedColor;
        // this.$emit("setHeaderStyle",this.pickedColor)
        // }else {
        // this.style.backgroundColor = "#232323";
        // //messageDisplay.textContent = "Try Again!";
        // this.$emit("setTextNavbar","Try Again!")
        // //messageDisplay.style.color = "#000000";
        // }
        },
      setAllColorsTo(color) {
        this.squares.forEach(function (square){
          square.style.backgroundColor = color
          })
          },
      PickColor(){
        return Math.floor(Math.random() * this.colorCount )
        },
      createNewColors(numbers){
        let arr = []
        for (let i = 0; i < numbers; i++) {
          arr.push(this.createRandomStringColor())
          }
          return arr
        },
      createRandomStringColor(){
        let newColor = "rgb(" + this.randomInt() + ", " + this.randomInt() + ", " + this.randomInt() + ")"
        return newColor
        },
      randomInt(){
        return Math.floor(Math.random() * 256)},
      restart(){
        this.destruirSquares()
        this.colorCount=this.isHard?6:3
        this.colors = this.createNewColors(this.colorCount)
        this.pickedColor = this.colors[this.PickColor()]
        this.crearSquares()
        this.$emit("colorDisplay",this.pickedColor)
        this.$emit("setTextNavbar","Pick New Colors!")
        this.$emit("setHeaderStyle","steelblue")
        this.$emit("setGameActive",false)
        }
    },
    events: {
        getColor: function (clickedColor) {
          console.log("COLOR CLICKEADO EN CONTAINER"+clickedColor)
            // logic
        }
}
  }

</script>

<style scoped lang="css">
.src-components-contenedor {
}
.square {
  width: 30%;
  background: blue;
  padding-bottom: 30%;
  float: left;
  margin: 1.66%;
  border-radius: 10%;
  transition: background 0.8s;
  -webkit-transition: background 0.8s;
  -moz-transition: background 0.8s;
}
#container {
  margin: 20px auto;
  max-width: 600px;
}
</style>
