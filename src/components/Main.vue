<template>
    <main>
        <div class="container">
        <h2>Film</h2>
        <div class="movies">    
            <MovieCard v-for="movie in moviesList" :key='movie.id' :moviesInfos="movie" />
        </div>

        <h2>Serie Tv</h2>
        <div class="series">
            <MovieCard v-for="serie in seriesList" :key='serie.id' :moviesInfos="serie"/>
        </div>
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

<style lang="scss" scoped>
main {
    background-color: #383838;
    padding: 20px 0;
}

.container .movies, .series {
    display: flex;
    overflow-x: auto;
}

h2 {
    margin-left: 10px;
    padding-top: 20px;
    font-size: 15px;
    text-transform: uppercase;
    color: white;
}

       
</style>