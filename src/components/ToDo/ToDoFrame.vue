<template>
  <div class="todo-frame-wrapper">
      <div class="title">Todo List</div>
        <ToDoOne :todos="todos" @remove="remove"/>
      <div class="input-wrapper">
          <input type="text" v-model="todo" placeholder="請輸入要做的事情">
          <div class="icon-wrapper" @click="AddTodo()">
              <svg width="21" height="18">
                  <image xlink:href="../../assets/add.svg"/>
              </svg>
          </div>
      </div>
  </div>
</template>

<script>
import { ref } from 'vue'
import ToDoOne from './ToDoOne.vue'

export default {
    components: {
        ToDoOne,
    },
    setup() {
        const todo = ref('')
        const todos = ref([])

        function AddTodo() {
            todos.value.push(todo.value)
            todo.value = ''
        }

        function remove(index) {
            todos.value.splice(index, 1)
        }

        return {
            AddTodo,
            todo,
            todos,
            remove,
        }
    }
}
</script>

<style lang="scss" scoped>
.todo-frame-wrapper {
    position: relative;
    width: 100%;
    max-width: 800px;
    height: 700px;
    margin: 16px auto;
    background: #FFFFFF;
    border: 1px solid #C7C3C6;
    box-sizing: border-box;
    border-radius: 4px;

    .title {
        margin: 33px 0 43px 30px;
        font-family: Roboto;
        font-size: 36px;
        font-weight: 700;
    }

    .icon-wrapper {
        display: flex;
        justify-content: center;
        align-items: center;
        width: 34px;
        height: 34px;
        background: #8DC8FF;
        border-radius: 4px;
    }
    .input-wrapper {
        display: flex;
        position: absolute;
        width: 100%;
        bottom: 10px;
        height: 34px;
        padding: 0 12px 0 17px;
        box-sizing: border-box;

        input {
            flex: 1 0 auto;
            margin-right: 25px;
            border: 1px solid #C7C3C6;
            border-radius: 4px;
            padding: 11px 14px;

            &::placeholder {
                color: #C1C1C1;
            }
        }
    }
}
</style>