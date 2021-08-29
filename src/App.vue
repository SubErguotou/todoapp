<template>
    <main>
    <div class="container">
      <h1>欢迎使用shun待办事项</h1>
      <div class="input-add">
      <input type="text" name="todo" />
      <button>
        <i class="plus"></i>
      </button>
      </div>
    </div>
    <div class="filters">
      <span class="fulter active">全部</span>
      <span class="fulter">已完成</span>
      <span class="fulter">未完成</span>
    </div>
    <div class="todo-list">
      <div class="todo-item">
        <lable>
          <input type="checkbox" />
          todo1
          <span class="check-button"></span>
        </lable>
      </div>
      <div class="todo-item">
        <lable>
          <input type="checkbox" />
          todo2
          <span class="check-button"></span>
        </lable>
      </div>
      <div class="todo-item">
        <lable>
          <input type="checkbox" />
          todo3
          <span class="check-button"></span>
        </lable>
      </div>
    </div>
  </main>
</template>

<script>
export default {
  name: 'App',
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
  background: rgb(203,210, 240);
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

.input-add{
  
}

</style>
