<template>
    <div>   
        todos
        <TodoItem/>
    </div>  
</template>

<script>
import TodoItem from "./TodoItem"
    export default {
        name:"Todos",
        components:{
            TodoItem,
        }
    }
</script>

<style lang="scss" scoped>
form {
    display: flex;
  }

  input[type="text"] {
    flex: 10;
    padding: 5px;
  }

  input[type="submit"] {
    flex: 2;
  }
</style>