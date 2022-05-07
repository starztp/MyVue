<template>
  姓：<el-input style="width:180px" v-model="person.firstname" size=large placeholder="请输入姓" />
  <br>
  名：<el-input style="width:180px" v-model="person.lastname" size=large placeholder="请输入名" />
  <br>
  全名：<el-input style="width:180px" v-model="person.fullname" size=large placeholder="请输入全名" />
  <br>
  个人信息：
  <br>
  姓：{{person.firstname}}
  <br>
  名：{{person.lastname}}
  <br>
  全名：{{person.fullname}}
  <br>
  显示信息：{{msg}}
  <br>
  <el-button @click="testHello" type="primary">触发hello事件</el-button>

</template>

<script>
import {reactive,computed,watch} from "vue";

export default {
  name: "Demo",
  props:["msg"],
  emits:['hello'],
  setup(props,context){
    let person = reactive({
      firstname:"",
      lastname:"",
      age:0
    })

    function testHello(){
      context.emit("hello",666)
    }

    person.fullname=computed({
      get(){
        return person.firstname+"_"+person.lastname
      },
      set(value){
        const nameArr = value.split("_")
        person.firstname = nameArr[0]
        person.lastname = nameArr[1]
      }
    })

    watch(person,()=>{
      console.log("person发生了变化")
    })

    return {
      person,
      testHello
    }
  }
}
</script>

<style scoped>

</style>