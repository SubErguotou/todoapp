<template>
  <div class="input-add">
    <input type="text" name="todo" v-model="todoContent" @keyup.enter="emitAddTodo"/>
    <button @click="emitAddTodo">
      <i class="plus"></i>
    </button>
  </div>
</template>

<script>

import { ref } from "vue"

export default {
    name: "TodoApp",
    // props:保存父组件传递下来的信息
    // context:保存了vue的上下文信息
    setup(props, context) {
        const todoContent = ref("");
        const emitAddTodo = ()=>{
            const todo = {
                id: props.tid,
                // v-model绑定的值可以使用.value取出
                content: todoContent.value,
                completed: false,
            }
            // 第一个参数事件名，第二个参数值
            context.emit("add-todo", todo);

            todoContent.value = "";
        }
        return{
            todoContent,
            emitAddTodo
        }
    }
};

</script>

<style lang="scss" scope>
.input-add {
  position: relative;
  display: flex;
  align-items: center;
}

.input-add input {
  padding: 16px 52px 16px 18px;
  border-radius: 48px;
  border: none;
  outline: none;
  box-shadow: 0px 0px rgba(0, 0, 0, 0.08);
  width: 100%;
  font-size: 16px;
  color: #626262;
}

// 圆形按钮
.input-add button {
  width: 46px;
  height: 46px;
  border-radius: 50%;
  background: linear-gradient(#c0a5f3, #7f95f7);
  border: none;
  outline: none;

  color: white;
  position: absolute;
  right: 0px;

  // 变成手指
  cursor: pointer;
}

// 添加代办事项里的十字
.input-add .plus {
  display: block;
  width: 100%;
  height: 100%;
  background: linear-gradient(#fff, #fff), linear-gradient(#fff, #fff);
  background-size: 50% 2px, 2px 50%;
  background-position: center;
  background-repeat: no-repeat;
}
</style>