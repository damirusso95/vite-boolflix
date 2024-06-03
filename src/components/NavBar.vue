<script>
import SearchBar from './SearchBar.vue';

export default {
  components: {
    SearchBar
  },
  methods: {
    handleSearchMovies(query) {
      this.$emit('search-movies', query);
    },
    handleSearchTv(query) {
      this.$emit('search-tv', query);
    }
  }
}
</script>

<template>
  <nav class="navbar">
    <h1>Boolflix</h1>
    <SearchBar @search-movies="handleSearchMovies" @search-tv="handleSearchTv" />
  </nav>
</template>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  padding: 1rem;
  background-color: #141414;
  color: white;
}
</style>
