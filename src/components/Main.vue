<template>
  <main>
      <Film v-for="movie in movies" :key="movie.id" 
      :title="movie.title"
      :orgTitle="movie.original_title"
      :language="movie.original_language"
      :vote="movie.vote_average"
      :poster="movie.poster_path"
      />
      <Series v-for="serie in series" :key="serie.id" 
      :title="serie.name"
      :orgTitle="serie.original_name"
      :language="serie.original_language"
      :vote="serie.vote_average"
      :poster="serie.poster_path"
      />
  </main>
</template>

<script>
import Film from "./Film.vue";
import Series from "./Series.vue";

export default {
    name:"Main",
    components:{
        Film,
        Series,
    },
    props:{
        movies: Array,
        series: Array,
    },
}
</script>

<style lang="scss">

</style>