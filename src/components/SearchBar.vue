<script>
export default {
    data() {
        return {
            query: ''
        };
    },
    methods: {
        searchMovies() {
            this.$emit('search-movies', this.query);
        },
        searchTv() {
            this.$emit('search-tv', this.query);
        }
    }
}
</script>
<template>
    <div class="search-bar">
        <input v-model="query" @keyup.enter="searchMovies" placeholder="Search for a movie or TV show..." />
        <button @click="searchMovies">Search Movies</button>
        <button @click="searchTv">Search TV Shows</button>
    </div>
</template>
<style scoped>
.search-bar {
    display: flex;
    align-items: center;
}

.search-bar input {
    padding: 0.5rem;
    font-size: 1rem;
    margin-right: 0.5rem;
}

.search-bar button {
    padding: 0.5rem 1rem;
    margin-left: 0.5rem;
    background-color: #e50914;
    color: white;
    border: none;
    cursor: pointer;
}
</style>