<template>
  <div id="app">
    <h1 ref="title">ref属性练习</h1>
    <button @click="showTitle">点我展示title</button>
    <School/>
    <Student/>
  </div>
</template>

<script>

import School from "./components/School";
import Student from "./components/Student";

export default {
  name: 'App',
  components: {
    School,
    Student
  },
  methods:{
    showTitle(){
      console.log(this.$refs.title)
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
