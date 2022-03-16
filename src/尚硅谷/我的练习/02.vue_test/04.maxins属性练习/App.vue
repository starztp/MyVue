<template>
  <div id="app">
    <h1 ref="title">maxins属性练习</h1>
    <Student name="天由哥" :age=18+1 />
    <School/>
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
