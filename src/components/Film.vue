<template>
  <div class="card">
    <img :src="`https://image.tmdb.org/t/p/w154${poster}`" :alt="title">
    <ul>
      <li>Titolo: {{title}}</li>
      <li>Titolo: {{orgTitle}}</li>
      <li>Lingua: <img v-if="Flags.includes(language)" :src="require(`@/boolflix-flags/${language}.png`)" :alt="language">
      <span v-else>{{language}}</span>
      </li>
      <li>Voto: <i v-for="i in 5" :key="i" :class="{yellowStar: i<voteConverter()}" class="fa-solid fa-star"></i></li>
    </ul>
  </div>
</template>

<script>
export default {
    name:"Film",
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
    },
    methods:{
      voteConverter(){
        return parseInt(this.vote/2)
      }
    }
}
</script>

<style lang="scss">
 .card{
   li{
     .yellowStar{
       color:yellow;
     }
     img{
       width: 25px;
     }
   }
 } 
</style>