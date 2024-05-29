<script>
export default {};
</script>

<template>
    <div class="movie-list">
        <div class="movie-item">
            <img src="https://via.placeholder.com/150" alt="Movie poster" />
            <h3>Titolo film</h3>
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
</style>