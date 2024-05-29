<script>
export default {
    props: {
        movies: Array
    },
    methods: {
        getPosterUrl(path) {
            return `https://image.tmdb.org/t/p/w500${path}`;
        }
    }
}
</script>

<template>
    <div class="movie-list">
        <div v-for="movie in movies" :key="movie.id" class="movie-item">
            <img :src="getPosterUrl(movie.poster_path)" alt="Movie poster" />
            <h3>{{ movie.title }}</h3>
            <p><strong>Original Title:</strong> {{ movie.original_title }}</p>
            <p><strong>Language:</strong> {{ movie.original_language }}</p>
            <p><strong>Rating:</strong> {{ movie.vote_average }}</p>
        </div>
    </div>
</template>
<style scoped>
.movie-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1rem;
    padding: 1rem;
}

.movie-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #222;
    padding: 1rem;
    border-radius: 10px;
    width: 200px;
}

.movie-item img {
    width: 150px;
    height: 225px;
    object-fit: cover;
    border-radius: 5px;
}

.movie-item h3 {
    margin-top: 0.5rem;
    font-size: 1rem;
    text-align: center;
}

.movie-item p {
    margin: 0.5rem 0;
    font-size: 0.9rem;
    text-align: center;
}
</style>