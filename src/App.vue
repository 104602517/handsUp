<template>
  <div>
    <Header :title="title" />
    <ToDoFrame />
  </div>
</template>

<script>
import Header from './components/Header/Header.vue'
import ToDoFrame from './components/ToDo/ToDoFrame.vue'
import { ref } from 'vue'

export default {
  components: {
    Header,
    ToDoFrame,
  },
  setup() {
    const title = ref('HandsUp')

    return {
      title,
    }
  },
}
</script>
<style>
* {
  padding: 0;
  margin: 0;
}

body {
  background: #E5E5E5;
}
</style>
