<template>
    <main>
        <div class="">
            <h2>Film</h2>
            <MovieCard v-for="movie in moviesList" :key='movie.id' :moviesInfos="movie" />
        
            <h2>Serie Tv</h2>
            <MovieCard v-for="serie in seriesList" :key='serie.id' :moviesInfos="serie"/>
        </div>
    </main>
</template>



<script>
import MovieCard from "./MovieCard.vue";



export default {
    name: "Main",
    components: {
        MovieCard,
    },
    props: {
        moviesList: Array,
        seriesList: Array
    }
}

</script>