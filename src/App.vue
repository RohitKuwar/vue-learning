<template>
  <Conditional />
</template>

<script>
import Conditional from './components/ListRendering.vue'

export default {
  name: 'App',
  components: {
    Conditional
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
