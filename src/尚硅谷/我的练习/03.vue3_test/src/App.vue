<template>
  <Demo @hello="showhello" msg="天由哥"/>
</template>

<script>
import Demo from "@/components/Demo";

export default {
  name: 'App',
  components: {
    Demo
  },
  setup(){
    function showhello(value){
      console.log(value)
    }
    return{
      showhello
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
