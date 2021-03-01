<template>
  <div class="todo-app">
    <TodoForm />
    <TodoList :todos="todos" />
  </div>
</template>

<style scoped>
.todo-app {
  width: 800px;
  margin: auto;
}
body {
  font-family: Helvetica sans-serif;
}
</style>

<script>
// @ is an alias to /src
import TodoList from "@/components/TodoList.vue";
import TodoForm from "@/components/TodoForm.vue";

export default {
  data() {
    return {
      todos: [
        {
          title: "My First TODO",
        },
      ],
    };
  },
  components: {
    TodoForm,
    TodoList,
  },

  methods: {
    addTodo(todo) {
      this.todos.push(todo);
    },
  },
};
</script>