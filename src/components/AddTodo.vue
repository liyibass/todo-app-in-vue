<template>
  <div>
    <form @submit="addTodo">
      <input
        type="text"
        v-model="title"
        name="title"
        placeholder="Add Todo..."
      />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
import { nanoid } from "nanoid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        id: nanoid(),
        title: this.title,
        completed: false,
      };

      //   Send to parents
      this.$emit("add-todo", newTodo);

      //   clear input
      this.title = "";
    },
  },
};
</script>

<style lang="scss" scoped>
form {
  display: flex;
  height: 50px;

  input[type="text"] {
    flex: 10;
    padding: 5px;
    &:focus {
      outline: none;
    }
  }

  input[type="submit"] {
    flex: 2;
  }
}
</style>
