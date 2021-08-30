<template>
  <div class="todo-list">
      <TodoListitemVue />
  </div>
</template>

<script>
import TodoListitemVue from './TodoListitem.vue';

export default {
    name: "TodoList",
    components: {
        TodoListitemVue
    }
};
</script>

<style lang="scss" scope>
.todo-list {
  display: grid;
  row-gap: 14px;
}
</style>