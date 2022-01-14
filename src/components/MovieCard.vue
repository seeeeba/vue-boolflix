<template>
    <div class="movie">
        <div class="cover">
            <div v-if="moviesInfos.poster_path" class="poster">
                <img :src="this.defaultPath + moviesInfos.poster_path"  :alt="moviesInfos.name">
            </div>
            <div v-else class="no-image">
                    Nessuna immagine disponibile
            </div>
        </div>
        <div v-if="moviesInfos.title" >Titolo: {{moviesInfos.title}}</div> 
        <div v-else>{{moviesInfos.name}}</div>
        <div v-if="moviesInfos.original_title">Titolo originale: {{moviesInfos.original_title}}</div> 
        <div v-else>Titolo originale: {{moviesInfos.original_name}}</div>
        <div>
            Lingua: 
            <span v-if="myFlags.includes(moviesInfos.original_language)">
                <img class="flag" :src="require(`../assets/img/${moviesInfos.original_language}.png`)" alt="">
            </span>

            <span v-else>
                {{moviesInfos.original_language}}
            </span>
        </div> 
        <div>Voto: 
            <span> <i v-for="(star,index) in Math.ceil((moviesInfos.vote_average) / 2)" :key="index" class="fas fa-star"></i> </span> 
            <span> <i v-for="(star,index) in ( 5 - Math.ceil((moviesInfos.vote_average) / 2))" :key="index" class="far fa-star"></i></span>
            
        </div> 
    </div>
</template>

<script>
export default {
    name: "MovieCard",
    data: function(){
        return{
            myFlags: ['it', 'en','fr','es'],
            defaultPath: 'https://image.tmdb.org/t/p/w342',            
        }
    },
    props: {
        moviesInfos: Object
    }
}
</script>

<style lang="scss" scoped>
// @import '../style/general.scss';
.movie {
    margin: 70px 10px;
    border: 2px solid white;
    height: 507px;
    width: 342px;
    cursor: pointer;
    flex-shrink: 0;
}

.flag{
    width: 30px;
}

.cover{
    height: 100%;
    width: 100%;
    overflow: hidden;
}


.no-image {
    position: relative;
    text-align: center;
    top: 50%;
    color: white;
}

</style>