<template>
  <div class="home">
    <h1>home</h1>
    <button @click="getMovies">data</button>
    <p v-for="movie in movies" :key="movie">{{ movie }}</p>
  </div>
</template>

<script>
// @ is an a

export default {
  name: "Home",
  components: {},
  props: ["getMovies", "movies"],
};
</script>
