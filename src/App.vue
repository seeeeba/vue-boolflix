<template>
  <div id="app">
    <Header @searchDone="search" />
    <Main :MoviesList="moviesArray" />
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
      apiKey: '869e287fe863ddfcc717d89513cac592',
      moviesArray:[]
    }
  },

  methods:{

    search:function(userString){
      this.queryValue = userString;
      this.getMovies();
    },

    getMovies: function(){
      axios.get(
        'https://api.themoviedb.org/3/search/movie',
        {
          params: {
            api_key: this.apiKey,
            query: this.queryValue
          }
        }
      ).then((response) => {
        this.moviesArray = response.data.results;
      });
    },
  }
};
</script>

<style lang="scss">

</style>
