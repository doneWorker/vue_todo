<template>
  <div class="Todo App">
    <TodoForm />
    <TodoList :todos="todos" />
  </div>
</template>

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