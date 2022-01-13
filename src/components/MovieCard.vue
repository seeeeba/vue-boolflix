<template>
    <div class="movie">
        <div>Titolo: {{infos.title}}</div> 
        <div>Titolo originale: {{infos.original_title}}</div> 
        <div>Lingua: {{infos.original_language}}</div> 
        <div>Voto {{infos.vote_average}}</div> 
    </div>
</template>

<script>
export default {
    name: "MovieCard",
    props: {
        infos: Object
    }
}
</script>

<style lang="scss" scoped>

.movie {
    margin: 2px 2px;
    border: 1px solid black;
}

</style>