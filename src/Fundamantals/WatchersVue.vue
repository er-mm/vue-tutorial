<template>
  <div>
    <h2>Volume tracker (0-20)</h2>
    <h3>Current Volume - {{ volume }}</h3>
    <div>
      <button @click="volume += 2">Increase</button>
      <button @click="volume -= 2">Decrease</button>
    </div>

    <input type="text" v-model="movie" />
    <input type="text" v-model="movieInfo.title" />
    <input type="text" v-model="movieInfo.actor" />

    <button @click="movieList = movieList.concat(['WonderWoman'])">Add Movie</button>
  </div>
</template>

<script>
export default {
  name: "WatchersVue",
  data() {
    return {
      volume: 0,
      movie: "Batman",
      movieInfo: {
        title: '',
        actor: ''
      },
      movieList: ['Batman', 'Superman']
    };
  },
  methods: {},
  computed: {},
  watch: {
    volume(newVal, oldVal) {
      if (newVal > oldVal && newVal === 16) {
        alert("high volume");
      }
    },
    movie: {
      handler(newVal) {
        console.log("Calling api with movie name = " + newVal);
      },
      immediate: true,
    },
    movieInfo: {
        handler(newVal) {
            console.log({title: newVal.title, actor: newVal.actor})
        },
        deep: true
    },
    movieList: {
        handler(newVal) {
            console.log(newVal)
        },
        // deep: true
    }
  },
};
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
</style>