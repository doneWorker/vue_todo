<template>
  <div id="todo-form">
    <input type="text" v-model="title" placeholder="Your Task" />
    <button id="add-todo" @click="submit">Add Todo</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "",
    };
  },
  methods: {
    submit() {
      this.$parent.addTodo({ title: this.title });
      this.title = "";
    },
  },
};
</script>