<template>
  <h2>{{ name }}</h2>
  <div>
    <button v-on:click="name = 'Batman'">Change name</button>
  </div>
  <h2>{{ count }}</h2>
  <div>
    <button v-on:click="count++">Increase</button>
    <button v-on:click="decrease">Decrease</button>
  </div>

  <!-- shorthand -->

  <h2>{{ name }}</h2>
  <div>
    <button @click="name = 'Batman'">Change name</button>
  </div>
  <h2>{{ count }}</h2>
  <div>
    <button @click="count++">Increase</button>
    <button @click="decrease">Decrease</button>
  </div>

  <!-- passing event props -->
  <h2>{{ name }}</h2>
  <div><button @click="changeName($event)">Change Name</button></div>
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      name: 'Kieu Duc',
      count: 0,
    }
  },
  methods: {
    decrease() {
      this.count--
    },
    changeName(event) {
      this.name = 'HCM'
      console.log('event', event)
    },
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
