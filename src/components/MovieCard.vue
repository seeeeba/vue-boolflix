<template>
    <div class="movie">
        <div v-if="moviesInfos.title" >Titolo: {{moviesInfos.title}}</div> 
        <div v-else>{{moviesInfos.name}}</div>
        <div v-if="moviesInfos.original_title">Titolo originale: {{moviesInfos.original_title}}</div> 
        <div v-else>Titolo originale: {{moviesInfos.original_name}}</div>
        <div>Lingua: {{moviesInfos.original_language}}</div> 
        <div>Voto: {{moviesInfos.vote_average}}</div> 
    </div>
</template>

<script>
export default {
    name: "MovieCard",
    props: {
        moviesInfos: Object
    }
}
</script>

<style lang="scss" scoped>

.movie {
    margin: 2px 2px;
    border: 1px solid black;
}

</style>