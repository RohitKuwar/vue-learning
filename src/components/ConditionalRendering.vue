<template>
  <div>
    <h1>Conditional Rendering</h1>
    <!-- The directive v-if is used to conditionally render a block. The block will only be rendered if the directive’s expression returns a truthy value. -->
    <h2 v-if="num === 0">Number is zero</h2>
    <h2 v-else-if="num < 0">Number is negative</h2>
    <h2 v-else-if="num > 0">Number is positive</h2>
    <h2 v-else>Not a Number</h2>

    <!-- template is same as React Fragment to avoid unnecessary node -->
    <template v-if="display">
      <h2>React</h2>
      <h2>Angular</h2>
      <h2>Vue</h2>
    </template>

    <!-- v-show will always be rendered and remain in the DOM; v-show only toggles the display CSS property of the element. -->
    <h2 v-show="showElement">Using v-show</h2>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        num: 10,
        display: true,
        showElement: true,
      }
    }
  }
</script>

<style scoped>

</style>