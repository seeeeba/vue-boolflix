<template>
  <div id="app">
    <Header @searchDone="search" />
    <Main :moviesList="moviesArray" :seriesList="seriesArray"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Main from "./components/Main.vue";


import axios from 'axios';

export default {
  name: "App",
  components: {
    Header,
    Main
  },

  data: function(){
    return{
      queryValue: '',
      api_key: '869e287fe863ddfcc717d89513cac592',
      moviesArray:[],
      seriesArray: []
    }
  },

  methods:{

    search:function(userString){
      this.queryValue = userString;
      this.getMovies();
      this.getSeries();
    },

    getMovies: function(){
      axios.get(
        'https://api.themoviedb.org/3/search/movie',
        {
          params: {
            api_key: this.api_key,
            query: this.queryValue
          }
        }
      ).then((response) => {
        this.moviesArray = response.data.results;
      });
    },
    getSeries: function(){
      axios.get(
        'https://api.themoviedb.org/3/search/tv',
        {
          params: {
            api_key: this.api_key,
            query: this.queryValue
          }
        }
      ).then((response)=>{
        this.seriesArray = response.data.results;
      })
    }
  }
};
</script>

<style lang="scss">

</style>
