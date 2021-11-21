<template lang="html">

  <section class="src-components-color" id="square" :style="myStyle" @click="click()">
  </section>

</template>

<script lang="js">
  export default  {
    name: 'src-components-color',
    props: [],
    data () {
      return {
        color:'',
        myStyle:{
            backgroundColor:"blue" 
            }
      }
    },
    methods: {
      click(){
        this.$emit('getColor',this.color)
        console.log("COLOR CLICKEADO: "+this.color);
      },
      setColor(setcolor){
        this.myStyle.backgroundColor= setcolor
        this.color = setcolor
      }
    },
    computed: {
    }
}


</script>

<style scoped lang="css">
  .src-components-color {

  }
  #square {
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
</style>
