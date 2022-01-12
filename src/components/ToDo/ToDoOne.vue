<template>
  <ul class="todos-wrapper">
      <li class="todo-wrapper" 
      v-for="(todo, index) in todos" 
      :key="`${todo}-index-${index}`">
        <div class="box-wrapper" @click="check($event)"></div>
        <div class="text-wrapper">{{todo}}</div>
        <div class="trash-wrapper" @click="remove(index)">
            <svg width="24" height="24">
                <image xlink:href="../../assets/trash.svg"/>
            </svg>
        </div>
      </li>
  </ul>
</template>

<script>
export default {
    props: ['todos'],
    emits: ['remove'],
    setup(_, context) {

        function check(ev) {
            const oLi = ev.target.parentElement
            if (oLi.classList.value.includes('checked')) {
                oLi.classList.remove('checked')
                return
            }
            oLi.classList.add('checked')
        }

        function remove(index) {
            context.emit('remove', index)
        }

        return {
            check,
            remove,
        }
    },
}
</script>

<style lang="scss" scoped>
.todo-wrapper {
    width: 100%;
    height: 60px;
    list-style: none;
    display: flex;
    align-items: center;
    padding: 0 52px;
    box-sizing: border-box;

    &.checked {
        color: #8DC8FF;

        .box-wrapper {
            background: url('../../assets/checkBox.svg');
        }
    }

    .box-wrapper {
        width: 22px;
        height: 19px;
        background: url('../../assets/box.svg');
        margin-right: 32px;
    }

    svg {
        vertical-align: middle;
        margin: 0 auto;
    }

    .text-wrapper {
        flex: 1 0 auto;
        height: 24px;
        line-height: 24px;
    }
}
</style>