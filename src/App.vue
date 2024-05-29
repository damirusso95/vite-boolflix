<script>
import NavBar from './components/NavBar.vue';
import MovieList from './components/MovieList.vue';

export default {
  components: {
    NavBar,
    MovieList
  }
}
</script>

<template>
  <div id="app">
    <NavBar />
    <MovieList />
  </div>
</template>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
