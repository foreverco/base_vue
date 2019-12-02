<template>
   <div class="todo-container">
    <div class="todo-wrap">
        <TodoHeader :addtodoLists='addtodoLists'></TodoHeader>
        <TodoList :todoLists='todoLists' :deltodoLists='deltodoLists'></TodoList>
        <TodoFooter :todoLists='todoLists' :delComplete='delComplete' :selectAllTodos='selectAllTodos'></TodoFooter>
    </div>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue'
import TodoList from './components/TodoList.vue'
import TodoFooter from './components/TodoFooter.vue'
export default {
  data () {
    return {
        todoLists:[
            {name:'吃饭',complete:false},
            {name:'睡觉',complete:true},
            {name:'coding',complete:false}
        ]
    };
  },
  components:{
      TodoHeader,
      TodoList,
      TodoFooter
  },
  methods: {
      addtodoLists(todo){
          this.todoLists.unshift(Object.assign(todo))
          
      },
      deltodoLists(index){
          this.todoLists.splice(index,1)
      },
      // 删除所有选中的todo
      delComplete(){
         this.todoLists = this.todoLists.filter(todo => !todo.complete)
      },
      // 全选/全不选
      selectAllTodos(check){
          this.todoLists.forEach(todo => todo.complete = check)
      }
  },
}

</script>
<style>



/*app*/
.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}





</style>