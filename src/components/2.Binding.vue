<template>
  <div>{{ name }}</div>
  <div v-text="text"></div>
  <div v-html="bold"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <h3 class="underline">static class underline text</h3>
  <h3 v-bind:class="status">static dinamic class</h3>
  <h3 v-bind:class="promote && 'success'">If clause in class</h3>
  <h3 v-bind:class="['underline', 'success']">Combine multiple class</h3>
  <h3
    v-bind:class="{
      promote: promote,
      new: !isSoldout,
      'sold-out': isSoldout,
    }"
  >
    Object conditional movie
  </h3>

  <h3
    v-bind:style="{
      color: highlightColor,
      fontSize: headerSize,
    }"
  >
    Inline style
  </h3>
  <h3 v-bind:style="styleObject">Style Object</h3>
  <h3 v-bind:style="[styleObject, successStyleObject]">Success Style Object</h3>

  <!-- shorthand syntax for v-bind -->
  <h3 :style="styleObject">Style Object</h3>
  <h3 :class="['underline', 'success']">Combine multiple class</h3>
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      name: 'Hello World',
      text: 'Im human',
      bold: '<b>Hight light</b>',
      headingId: 'H2Id',
      status: 'success',
      promote: true,
      isSoldout: false,
      highlightColor: 'orange',
      headerSize: 50,
      styleObject: {
        color: 'orange',
        fontSize: '50px',
      },
      successStyleObject: {
        color: 'green',
      },
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
