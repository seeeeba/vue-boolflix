<template>
    <main>
        <div class="">
            <h2>Film</h2>
            <MovieCard v-for="movie in moviesList" :key='movie.id' :moviesInfos="movie" />
        </div>
        <div class="">
            <h2>Serie Tv</h2>
            <SeriesCard v-for="serie in seriesList" :key='serie.id' :seriesInfos="serie"/>
        </div>
    </main>
</template>



<script>
import MovieCard from "./MovieCard.vue";
import SeriesCard from './SeriesCard.vue';


export default {
    name: "Main",
    components: {
        MovieCard,
        SeriesCard
    },
    props: {
        moviesList: Array,
        seriesList: Array
    }
}

</script>