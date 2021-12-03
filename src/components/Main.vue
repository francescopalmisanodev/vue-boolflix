<template>
  <main>
      <Film v-for="movie in movies" :key="movie.id" 
      :title="movie.title"
      :orgTitle="movie.original_title"
      :language="movie.original_language"
      :vote="movie.vote_average"
      :poster="movie.poster_path"
      :overview="movie.overview"
      />
      <Film v-for="serie in series" :key="serie.id" 
      :title="serie.name"
      :orgTitle="serie.original_name"
      :language="serie.original_language"
      :vote="serie.vote_average"
      :poster="serie.poster_path"
      :overview="serie.overview"
      />
  </main>
</template>

<script>
import Film from "./Film.vue";

export default {
    name:"Main",
    components:{
        Film,
    },
    props:{
        movies: Array,
        series: Array,
    },
}
</script>

<style lang="scss">
main{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    max-width: 1180px;
    margin:0 auto;
}
</style>