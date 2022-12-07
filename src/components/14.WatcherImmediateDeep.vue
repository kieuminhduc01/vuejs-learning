<template>
  <!-- watchers
  theo dõi giá trị của data 

  watchers vs computed properties
  computed properties:
    * dùng khi biên soạn lại data đã có sẵn.
    * có thể dùng để giảm chiều dài của biến.
  watchers:
    * dùng khi check 1 property có sử thay đổi và sự thay đổi đó sẽ dẫn tới 1 hành động cụ thể.
    * dùng để call API và response trả về làm thay đổi data của app -->
  <h2>volume tracker (0-20)</h2>
  <h3>current volume: {{ volume }}</h3>
  <div>
    <button @click="volume += 2">Increase</button>
    <button @click="volume -= 2">Decrease</button>
  </div>
  <input type="text" v-model="movie" />
  <input type="text" v-model="movieInfo.title" />
  <input type="text" v-model="movieInfo.actor" />
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      volume: 0,
      movie: 'batman',
      movieInfo: {
        title: '',
        actor: '',
      },
    }
  },
  methods: {},
  computed: {},
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert('Listening to a high volume for a long time may damage your hearing')
      }
    },
    movie: {
      handler(newValue) {
        console.log(`Calling api with movie name ${newValue}`)
      },
      // immediate = true watcher sẽ được gọi luôn khi component sinh
      immediate: true,
    },
    movieInfo: {
      handler(newValue) {
        console.log(
          `Calling api with movie title = ${newValue.title} and actor = ${newValue.actor}`,
        )
      },
      // deep = true watcher sẽ được gọi khi data có sự thay đổi
      deep: true,
    },
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
}
.new {
  color: olivedrab;
}
.sold-out {
  color: red;
}
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}
input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}
input[type='text'],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
