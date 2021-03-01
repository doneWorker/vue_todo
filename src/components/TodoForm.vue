<template>
  <div id="todo-form">
    <input
      type="text"
      v-model="title"
      placeholder="Your Task"
      class="todo-input"
      @keyup="onChange"
      v-bind:class="{ 'has-error': hasError }"
    />
    <button id="add-todo" class="add-todo" @click="submit">Add Todo</button>
    <br clear="both" />
  </div>
</template>

<style scoped>
.todo-input {
  width: 100%;
  font-size: 20px;
  line-height: 2.5;
  margin: 5px 0;
  border: none;
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.5);
}
.todo-input.has-error {
  border: 2px solid red;
}
.todo-input:focus {
  outline: none;
  box-shadow: 0 0 5px cadetblue;
}
.add-todo {
  width: 200px;
  line-height: 50px;
  font-size: 1.1em;
  float: right;
  background: cadetblue;
  color: white;
  text-transform: uppercase;
  border: none;
  transition: background-color 0.5s;
}
.add-todo:hover {
  background: darkcyan;
}
</style>

<script>
export default {
  data() {
    return {
      hasError: false,
      title: "",
    };
  },
  methods: {
    onChange() {
      this.checkIsError();
    },
    checkIsError() {
      this.hasError = this.title.length < 3 ? true : false;
    },
    submit() {
      this.checkIsError();
      if (!this.hasError) {
        this.$parent.addTodo({ title: this.title, completed: false });
        this.title = "";
      }
    },
  },
};
</script>