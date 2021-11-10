<template>
  <div id="nav">
    <router-link to="/" :getMovies="getMovies">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
  <router-view />
  <!-- <button @click="getData">Get me</button> -->
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      url: "https://api.themoviedb.org/3/search/movie?api_key=0150f230986e887a5efff2e0af9009b0&query=Jack",
      movies: [],
    };
  },
  methods: {
    getMovies() {
      fetch(this.url)
        .then((response) => response.json())
        .then((data) => {
          this.movies = data;
        });
    },
  },

  // created() {
  //   this.getData();
  // },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
