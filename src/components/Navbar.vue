<template lang="html">
  <section class="src-components-navbar" id="navigator">
		<button id="reset" @click="Reset()"> {{gameActive?'New colors':'Play again!'}}</button>
		<span id="message">{{message}}</span>
		<button id="easy" @click="Easy()" v-bind:class="[{ 'selected': !hard }, '']">easy</button>
		<button id="hard" @click="Hard()" v-bind:class="[{ 'selected': hard }, '']">hard</button>
  </section>  
</template>

<script>

  export default  {
    name: 'src-components-navbar',
    props: [],
    data () {
      return {
        message:'',
        hard: '',
        gameActive:'',
      }
    },
    methods: {
      getInicialData() {
      return {
        message:'',
        hard: true,
        gameActive:false,
      }
    },
      Reset(){
        this.gameActive=true
        this.$emit('setDificult',this.hard)
      },
      Easy(){        
            this.hard = false;
            this.Reset();
      },
      Hard(){        
            this.hard = true;
            this.Reset();
          }
    }
}


</script>

<style scoped lang="css">
.src-components-navbar {
}
#navigator {
  background: #ffffff;
  height: 30px;
  text-align: center;
  margin: 0;
  margin-top: -30px;
}
#message {
  color: #ffffff;
  display: inline-block;
  width: 20%;
}
.selected {
  background-color: steelblue;
  color: white;
}
button {
  border: none;
  background-color: white;
  font-family: "Montserrat", "Avenir";
  text-transform: uppercase;
  height: 100%;
  font-weight: 700;
  letter-spacing: 1px;
  color: steelblue;
  transition: all 0.3s;
  outline: none;
}
button:hover {
  color: white;
  background-color: steelblue;
}
</style>
