<template>
    <div class="movie">
        <div class="cover">
            <div v-if="moviesInfos.poster_path" class="poster">
                <img :src="this.defaultPath + moviesInfos.poster_path"  :alt="moviesInfos.name">
            </div>
            <div v-else class="no-image">
                <span>Nessuna cover disponibile</span> 
            </div>
        </div>
        <div class="card">
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

            <div v-if="moviesInfos.overview" class="overview">
                <span class="bold">
                    Overview:
                </span>
                {{ moviesInfos.overview }}
            </div>
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
    margin: 30px 10px;
    height: 507px;
    width: 342px;
    cursor: pointer;
    flex-shrink: 0;
}

.movie:hover .cover{
    display: none;
}

.movie:hover .card{
    display: block;
}

.flag{
    width: 30px;
}

.cover img{
    height: 507px;
    width: 100%;
    overflow: hidden;
}


.no-image {
    height: 507px;
    width: 342px;  
     
        span{
        position: relative;
        text-align: center;
        top:50%;
        color: white;
        }
}

</style>