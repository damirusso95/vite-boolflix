<script>
import NavBar from './components/NavBar.vue';
import MovieList from './components/MovieList.vue';

export default {
  components: {
    NavBar,
    MovieList
  },
  data() {
    return {
      movies: []
    };
  },
  methods: {
    async fetchMovies(query) {
      const apiKey = 'a703c03fadaef93da97b114d84d7c5a1'; 
      const response = await fetch(`https://api.themoviedb.org/3/search/movie?api_key=${apiKey}&query=${query}`);
      const data = await response.json();
      this.movies = data.results;
    }
  }
}
</script>

<template>
  <div id="app">
    <NavBar @search="fetchMovies" />
    <MovieList :movies="movies" />
  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
