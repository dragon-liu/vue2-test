<template>
  <div class="todo-footer" v-show="allTodo">
    <label>
      <input type="checkbox" v-model="isAll"/>
    </label>
    <span>
      <span>已完成{{todoDone}}</span> / 全部{{allTodo}}
    </span>
    <button class="btn btn-danger" @click="clearDone">清除已完成任务</button>
  </div>
</template>

<script>
export default {
  name:'MyFooter',
  props:['todos'],
  methods:{
    clearDone(){
      // this.clearAllDone()
      this.$emit('clearAllDone')
    }
  },
  computed:{
    todoDone(){
      console.log(this)
      return this.todos.reduce((pre,todo)=>{return pre + (todo.done?1:0) }, 0) //NOTE:注意三元运算符优先级
    },
    allTodo(){
      return this.todos.length
    },
    isAll:{
      get(){
        return this.todoDone === this.allTodo
      },
      set(value){
        // this.checkAll(value)
        this.$emit('checkAll', value)
      }
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