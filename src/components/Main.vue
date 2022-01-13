<template>
    <main>
        <h2>Film</h2>
        <MovieCard v-for="movie in moviesList" :key='movie.id' />
    </main>
</template>



<script>
import MovieCard from "./MovieCard.vue";

export default {
    name: "Main",
    components: {
        MovieCard
    },
    props: {
        MoviesList: Array
    }
}

</script>