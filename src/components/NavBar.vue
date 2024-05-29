<script>
import SearchBar from './SearchBar.vue';

export default {
  components: {
    SearchBar
  }
}
</script>

<template>
  <nav class="navbar">
    <h1>Boolflix</h1>
    <SearchBar />
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
