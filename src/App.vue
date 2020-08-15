<template>
  <div id="app">
    <Header />
    <AddTodos v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodos from "./components/AddTodo";
import Header from "./layout/Header";

export default {
  name: "App",
  components: {
    Todos,
    Header,
    AddTodos,
  },

  data() {
    return {
      todos: [
        {
          id: 1,
          title: "todo 1",
          completed: false,
        },
        {
          id: 2,
          title: "todo 2",
          completed: false,
        },
        {
          id: 3,
          title: "todo 3",
          completed: false,
        },
      ],
    };
  },

  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    },
  },
};
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.btn {
  display: inline-block;
  border: none;
  background: #555;
  padding: 7px 20px;
  cursor: pointer;

  &:hover {
    background: #666;
  }
}
</style>
