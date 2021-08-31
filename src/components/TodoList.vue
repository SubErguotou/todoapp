<template>
  <div class="todo-list">
    <TodoListitemVue 
      	v-for="todo in todos" 
    	:key="todo.id" 
		:todo-item="todo"
		@change-state="todo.completed = $event.target.checked">
		</TodoListitemVue>
  </div>
</template>

<script>
import TodoListitemVue from "./TodoListitem.vue";

export default {
  name: "TodoList",
  components: {
    TodoListitemVue,
  },
  props: ["todos"],
};
</script>

<style lang="scss" scope>
.todo-list {
  display: grid;
  row-gap: 14px;
}
</style>