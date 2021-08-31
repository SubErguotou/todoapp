<template>
   <main>
    <div class="container">
      <h1>欢迎使用shun待办事项</h1>
      <!-- @add-todo子组件传过来的方法名，addTodo绑定的方法-->
      <TodoAddVue :tid="todos.length" @add-todo = "addTodo"/>
      <!-- 使用$event可以获取到子组件传递过来的值 -->
      <TodoFilterVue :selected="filter" @change-filter="filter = $event"/>
      <TodoListVue :todos="filteredTodos"/>
    </div>
  </main>
</template>

<script>
import { computed, ref } from "vue";
import TodoAddVue from './components/TodoAdd.vue'
import TodoFilterVue from './components/TodoFilter.vue'
import TodoListVue from './components/TodoList.vue'


export default {
  name: 'App',
  components: {
    TodoAddVue,
    TodoFilterVue,
    TodoListVue
  },
  setup() {
    const todos = ref([]);
    const addTodo = (todo) => todos.value.push(todo);

    const filter = ref("all");

    const filteredTodos = computed(() => {
      switch (filter.value){
        case "done":
          return todo.value.filter((todo) => todo.completed);
        case "todo":
          return todo.value.filter((todo) => !todo.completed);
        default:
          return todos.value;
      }
    })

    return {
      todos,
      addTodo,
      filteredTodos,
      filter
    }
  }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Helvetica, "PingFang SC", "Microsoft Yahei", sans-serif;
}

main {
  width: 100vw;
  min-height: 100vh;
  display: grid;
  align-items: center;
  justify-items: center;
  background: rgb(203, 210, 240);
}

.container {
  width: 60%;
  max-width: 400px;
  box-shadow: 0px 0px 24px rgba(0, 0, 0, 0.15);
  border-radius: 24px;
  padding: 48px 28px;
  background-color: rgb(245, 246, 252);
}

h1 {
  margin: 24px 0;
  font-size: 28px;
  color: #414873;
}

</style>
