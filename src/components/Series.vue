<template>
  <div class="card">
    <img :src="`https://image.tmdb.org/t/p/w154${poster}`" :alt="title">
    <ul>
      <li>Titolo della Serie: {{title}}</li>
      <li>Titolo originale della Serie: {{orgTitle}}</li>
      <li>Lingua della Serie: <img v-if="Flags.includes(language)" :src="require(`@/boolflix-flags/${language}.png`)" :alt="language">
      <span v-else>{{language}}</span>
      </li>
      <li>Voto della Serie: {{vote}}</li>
    </ul>
  </div>
</template>

<script>
export default {
    name:"Series",
    data(){
      return{
        Flags: ["it", "en"],
      }
    },
    props: {
      title:String,
      orgTitle:String,
      language:String,
      vote:Number,
      poster:String,
    }
}
</script>

<style lang="scss">
</style>