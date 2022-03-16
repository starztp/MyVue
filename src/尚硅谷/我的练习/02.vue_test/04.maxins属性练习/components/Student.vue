<template>
  <div>
    <h2>学生姓名：{{name}}</h2>
    <h2>学生年龄：{{age}}</h2>
    <button @click="showName">点我展示名称</button>
  </div>
</template>

<script>
import {mix} from "@/mixin";

export default {
  name: "Student",
  props:{
    name:{
      type: String,
      required: true
    },
    age:{
      type: Number,
      required: true
    },
    sex:{
      type: String,
      required: false
    }
  },
  mixins:[mix]
}
</script>

<style scoped>

</style>