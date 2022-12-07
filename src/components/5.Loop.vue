<template>
  <h2 v-for="name in names" :key="name">{{ name }}</h2>
  <h2 v-for="(name, index) in names" :key="index">{{ name }}-{{ index }}</h2>
  <h2 v-for="(name, index) in fullNames" :key="index">{{ name.first }} {{ name.last }}</h2>
  <div v-for="actor in actors" :key="actor.name">
    <h2>{{ actor.name }}</h2>
    <h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>
  </div>

  <h2 v-for="(value, key, index) in myInfo" :key="index">{{ index }}-{{ key }}-{{ value }}</h2>
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      names: ['Duc', 'Thanh', 'Nguyen'],
      fullNames: [
        { first: 'Kieu', last: 'Duc' },
        { first: 'Le', last: 'Thanh' },
        { first: 'Pham', last: 'Nguyen' },
      ],
      actors: [
        {
          name: 'The Rocks',
          movies: ['Black Adam', 'Fast and Furious'],
        },
        {
          name: 'Vinh Rau',
          movies: ['FapTV'],
        },
      ],
      myInfo: {
        name: 'Kieu Minh Duc ',
        age: 23,
        gender: 'Male',
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
