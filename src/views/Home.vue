<template>
  <div class="home">
    <AddTodo @add-todo="addTodo" />
    <Todos :todos="todos" @del-todo="deleteTodo" />
  </div>
</template>

<script>
import AddTodo from "../components/AddTodo";
import Todos from "../components/Todos";
import axios from "axios";
export default {
  name: "Home",
  components: {
    AddTodo,
    Todos,
  },
  data() {
    return {
      todos: [],
    };
  },
  mounted() {
    axios
      .get("https://jsonplaceholder.typicode.com/todos?_limit=5")
      .then((res) => (this.todos = res.data))
      .catch((err) => console.log(err));
  },
  methods: {
    addTodo(newTodo) {
      const { title, completed } = newTodo;
      axios
        .post("https://jsonplaceholder.typicode.com/todos", {
          title,
          completed,
        })
        .then((res) => (this.todos = [...this.todos, res.data]))
        .catch((err) => console.log(err));
   
    },
    deleteTodo(id) {
      alert(id);
      console.log(id);
      axios
        .delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then(
          (res) => (this.todos = this.todos.filter((todo) => todo.id !== id))
        )
        .catch((err) => console.log(err));
    },
  },
};
</script>
