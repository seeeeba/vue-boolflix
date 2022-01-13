<template>
    <div class="serie">
        <div>Titolo: {{seriesInfos.name}}</div> 
        <div>Titolo originale: {{seriesInfos.original_name}}</div> 
        <div>Lingua: {{seriesInfos.original_language}}</div> 
        <div>Voto: {{seriesInfos.vote_average}}</div> 
    </div>
</template>

<script>
export default {
    name: "SeriesCard",
    props: {
        seriesInfos: Object
    }
}
</script>

<style lang="scss" scoped>

.serie {
    margin: 2px 2px;
    border: 1px solid black;
}


</style>