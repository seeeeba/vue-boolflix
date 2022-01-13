<template>
    <main>
        <h2>Film</h2>
        <MovieCard v-for="movie in moviesList" :key='movie.id' :infos="movie" />
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
        moviesList: Array
    }
}

</script>