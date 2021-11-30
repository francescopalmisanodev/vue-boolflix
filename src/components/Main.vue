<template>
  <main>
      <Film v-for="movie in movies" :key="movie.id" 
      :title="movie.title"
      :orgTitle="movie.original_title"
      :language="movie.original_language"
      :vote="movie.vote_average"
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
    },
}
</script>

<style lang="scss">

</style>