<template>
   <ul class="todo-main">
            <TodoItem v-for="(item, index) in todoLists" :key="index" :item='item' :index='index' :todoLists='todoLists' :deltodoLists='deltodoLists'></TodoItem>
      </ul>
</template>

<script>
import TodoItem from './TodoItem'
export default {
    props:{
        deltodoLists:Function,
        todoLists:{
            type:Array
        },
    },
    components:{
        TodoItem
    },
  data () {
    return {

    };
  },

}

</script>
<style>

/*main*/
.todo-main {
  margin-left: 0px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0px;
}

.todo-empty {
  height: 40px;
  line-height: 40px;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding-left: 5px;
  margin-top: 10px;
}

</style>