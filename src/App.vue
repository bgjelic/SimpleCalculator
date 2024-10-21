<template>
  <div id="app">
    <Calculator />
  </div>
</template>

<script>
// Import the Calculator component
import Calculator from './components/Calculator.vue'

export default {
  components: {
    Calculator
  }
}
</script>

<style>
#app {
  text-align: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>