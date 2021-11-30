<template>
<div class="container">
  <Header @search="searchFilm"/>
  <Main :movies="searchedFilm"/>
</div>
</template>

<script>
import Main from './components/Main.vue';
import Header from './components/Header.vue';
import axios from "axios";

export default {
  name: 'App',
  data(){
    return {
      searchedFilm:[],
    }
  },
  components: {
    Header,
    Main,
  },
  methods: {
    searchFilm(searchString){
      axios.get("https://api.themoviedb.org/3/search/movie?", 
      {
        params:{
          api_key:"9c9f4b2fc3a4b58cc440f2799bd177f1",
          query: `${searchString}`,
        }
      })
      .then(result=>{
        this.searchedFilm=result.data.results;
      }).catch(err=>console.error(err));
    },
  }
}
</script>

<style lang="scss">

</style>
