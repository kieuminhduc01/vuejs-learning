<template>
  <!-- conditional rendering -->
  <!-- v-if (the element do or dont  mount the dom)-->
  <!-- v-else -->
  <!-- v-else-if -->
  <!-- v-show (the element have display prop is 'none' or not)-->
  <h2 v-if="num === 0">The number is zero</h2>
  <h2 v-else-if="num < 0">The number is negative</h2>
  <h2 v-else-if="num > 0">The number is positive</h2>
  <h2 v-else>The number is not a number</h2>

  <template v-if="true">
    <h2>ReactJs</h2>
    <h2>VueJs</h2>
  </template>

  <h2 v-show="vShow">v show is true</h2>
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      num: 'Hello',
      vShow: false,
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}

.success {
  color: orange;
}
</style>
