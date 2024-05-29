<script>
export default {};
</script>

<template>
    <div class="search-bar">
        <input placeholder="Cerca un film..." />
        <button>Search</button>
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
    background-color: #e50914;
    color: white;
    border: none;
    cursor: pointer;
}
</style>