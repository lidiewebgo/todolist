<template>
  <div class="home">
    <AddTodo @add-todo="addTodo"/>
    <Todos/>
  </div>
</template>

<script>
import AddTodo from "../components/AddTodo"
import Todos from "../components/Todos"
export default {
  name: 'Home',
  components: {
    AddTodo,
    Todos
  },
  data(){
    return{
      todos:[]
    }
  },
  methods:{
    addTodo(newTodo){
      alert(123444)
      const {title,completed} = newTodo;
      console.log(newTodo)

    }
  }
}
</script>
