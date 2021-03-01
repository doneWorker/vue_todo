<template>
  <ol class="todo-list">
    <li v-for="(todo, idx) in todos" :key="idx">
      {{ todo.title }}
      <label
        >Completed: <input type="checkbox" @checked="todo.completed"
      /></label>
    </li>
  </ol>
</template>

<style scoped>
li {
  width: 100%;
  min-height: 50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-sizing: border-box;
  padding: 0 10px;
}
li:nth-child(even) {
  background: #f1f1f1;
}
</style>

<script>
export default {
  props: ["todos"],
  data() {},
};
</script>