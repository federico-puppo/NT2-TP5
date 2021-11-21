<template lang="html">
	<section class="src-components-header" id="header">
		<h1>The Great <br>
			<span id="colorDisplay">{{rgb}}</span>
			<br>
			Guessing Game</h1>
    <br>
</section>
</template>

<script lang="js">

export default  {
    name: 'src-components-header',
    props: [],
    data () {
    return {
        rgb: '',
    }
    },
    methods: {
      init(){
        if (!this.rgb){
          this.rgb=''
          //console.log("COLOR SETEADO EN NULL");
          }
      }

    },
    computed: {

    }
}


</script>

<style scoped lang="css">
.src-components-header {
  background: #232323;
  margin: 0;
  font-family: "Montserrat", "Avenir";
}
#header {
  transition: all 0.3s;
  background: steelblue;
  text-transform: uppercase;
  text-align: center;
  margin: 0;
  color: white;
}
#colorDisplay {
  font-size: 200%;
}

h1 {
  font-weight: normal;
  line-height: 1.1;
  padding: 20px 0;
}
body {
  background: #232323;
  margin: 0;
  font-family: "Montserrat", "Avenir";
}
</style>
