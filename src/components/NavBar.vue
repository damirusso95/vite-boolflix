<script>
import SearchBar from './SearchBar.vue';

export default {
  components: {
    SearchBar
  },
  methods: {
    handleSearch(query) {
      this.$emit('search', query);
    }
  }
}
</script>

<template>
  <nav class="navbar">
    <h1>BoolFlix</h1>
    <SearchBar @search="handleSearch" />
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
