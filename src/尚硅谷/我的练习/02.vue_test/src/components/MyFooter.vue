<template>
  <div class="todo-footer">
    <label>
      <input type="checkbox" v-model="isAll"/>
    </label>
    <span>
          <span>已完成{{doneCount}}</span> / 全部{{todoList.length}}
        </span>
    <button class="btn btn-danger" @click="clearAllDone">清除已完成任务</button>
  </div>
</template>

<script>
export default {
  name: "MyFooter",
  props: ["todoList","clearAllDoneTodo","checkAllTodo"],
  computed: {
    doneCount(){
      let i = 0
      this.todoList.forEach((todo)=>{
        if(todo.is_done){
          i++
        }
      })
      return i
    },
    isAll:{
      get(){
        return this.doneCount === this.todoList.length && this.todoList.length>0
      },
      set(value){
        console.log(value)
        this.checkAllTodo(value)
      }
    }
  },
  methods:{
    clearAllDone(){
      this.clearAllDoneTodo()
    }
  }
}
</script>

<style scoped>
/*footer*/
.todo-footer {
  height: 40px;
  line-height: 40px;
  padding-left: 6px;
  margin-top: 5px;
}

.todo-footer label {
  display: inline-block;
  margin-right: 20px;
  cursor: pointer;
}

.todo-footer label input {
  position: relative;
  top: -1px;
  vertical-align: middle;
  margin-right: 5px;
}

.todo-footer button {
  float: right;
  margin-top: 5px;
}

</style>