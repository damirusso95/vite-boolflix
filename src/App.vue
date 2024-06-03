<script>
import NavBar from './components/NavBar.vue';
import MovieList from './components/MovieList.vue';
import axios from 'axios';

export default {
  components: {
    NavBar,
    MovieList
  },
  data() {
    return {
      movies: [],
      tvShows: []
    };
  },
  methods: {
    async fetchMovies(query) {
      const apiKey = 'a703c03fadaef93da97b114d84d7c5a1';  // Sostituisci con la tua chiave API
      const language = 'it_IT'; // Sostituisci con la lingua desiderata
      try {
        const response = await axios.get(`https://api.themoviedb.org/3/search/movie`, {
          params: {
            api_key: apiKey,
            query,
            language
          }
        });
        this.movies = response.data.results.map(movie => ({
          id: movie.id,
          title: movie.title,
          original_title: movie.original_title,
          original_language: movie.original_language,
          vote_average: movie.vote_average,
          poster_path: movie.poster_path
        }));
      } catch (error) {
        console.error('Error fetching movies:', error);
      }
    },
    async fetchTvShows(query) {
      const apiKey = 'a703c03fadaef93da97b114d84d7c5a1';
      const language = 'it_IT';
      try {
        const response = await axios.get(`https://api.themoviedb.org/3/search/tv`, {
          params: {
            api_key: apiKey,
            query,
            language
          }
        });
        this.tvShows = response.data.results.map(tv => ({
          id: tv.id,
          title: tv.name,
          original_title: tv.original_name,
          original_language: tv.original_language,
          vote_average: tv.vote_average,
          poster_path: tv.poster_path
        }));
      } catch (error) {
        console.error('Error fetching TV shows:', error);
      }
    }
  }
}
</script>
<template>
  <div id="app">
    <NavBar @search-movies="fetchMovies" @search-tv="fetchTvShows" />
    <div class="results">
      <div>
        <h2>Movies</h2>
        <MovieList :items="movies" type="movie" />
      </div>
      <div>
        <h2>TV Shows</h2>
        <MovieList :items="tvShows" type="tv" />
      </div>
    </div>
  </div>
</template>
<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.results {
  display: flex;
  justify-content: space-around;
}
</style>
