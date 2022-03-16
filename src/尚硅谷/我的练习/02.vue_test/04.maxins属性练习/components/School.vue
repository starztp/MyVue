<template>
  <div>
    <h2>学校名称{{name}}</h2>
    <h2>学校地址{{address}}</h2>
    <button @click="showName">点我展示名称</button>
  </div>
</template>

<script>
import {mix} from "@/mixin";

export default {
  name: "School",
  data(){
    return {
      name: "青麦",
      address: "汶水路"
    }
  },
  mixins: [mix]
}
</script>

<style scoped>

</style>