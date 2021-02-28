<template>
  <div class="todo-list">
    <li v-for="(todo, idx) in todos" :key="idx">
      {{ todo.title }}
    </li>
  </div>
</template>


<script>
export default {
  props: ["todos"],
  data() {},
};
</script>