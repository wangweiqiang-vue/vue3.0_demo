<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h3>{{ state.num1 }}</h3>
    <h3>{{ state.num2 }}</h3>
    <h3>{{ state.result }}</h3>
  </div>
</template>

<script>
import {
  reactive,
  computed,
  onMounted,
  onUpdated,
  onBeforeUnmount,
  onUnmounted
} from 'vue'

const state = reactive({
  num1: 0,
  num2: 1,
  result: computed(() => state.num2 + state.num1)
})

function add() {
  state.result = state.num1 + state.num2
}

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup() {
    return {
      state,
      add
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
