<template>
    <div class="movie">
        <div>Titolo: {{moviesInfos.title}}</div> 
        <div>Titolo originale: {{moviesInfos.original_title}}</div> 
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