<template>
  <div id="app">
    Clicked: {{ $store.state.count }} times, count is {{ evenOrOdd }}.
    <button @click="increment">+</button>
    <button @click="decrement">-</button>
    <button @click="incrementIfOdd">Increment if odd</button>
    <button @click="incrementAsync">Increment async</button>
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex'

export default {
  // mapGetters 辅助函数仅仅是将 store 中的 getter 映射到局部计算属性：
  computed: mapGetters([
    'evenOrOdd'
  ]),
  methods: mapActions([
    // mapActions将 `this.increment()` 映射为 `this.$store.dispatch('increment')`
    'increment',
    // vuex使用store.dispatch('increment')来触发方法
    'decrement',
    'incrementIfOdd',
    'incrementAsync'
  ])
}
</script>
