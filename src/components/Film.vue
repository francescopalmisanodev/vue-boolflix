<template>
  <div class="card">
    <img v-if="poster" :src="`https://image.tmdb.org/t/p/w342${poster}`" :alt="title">
    <img v-else src="https://www.repstatic.it/content/nazionale/img/2013/11/13/140555543-efd9a67a-c4d7-48e5-80d6-2c1583b2c752.jpg?webp" :alt="title">
    <ul>
      <li>Titolo: {{title}}</li>
      <li>Titolo: {{orgTitle}}</li>
      <li>Lingua: <img v-if="Flags.includes(language)" :src="require(`@/boolflix-flags/${language}.png`)" :alt="language">
      <span v-else>{{language}}</span>
      </li>
      <li>Voto: <i v-for="i in 5" :key="i" :class="{yellowStar: i<voteConverter()}" class="fa-solid fa-star"></i></li>
      <li>Overview:{{overview}}</li>
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
      overview:String,
    },
    methods:{
      voteConverter(){
        return parseInt(this.vote/2)
      }
    }
}
</script>

<style lang="scss">
@import "../scss/variables.scss";
 .card{
   width:20%;
   height: 350px;
   margin:20px;
   border:3px solid black;
   position: relative;
   overflow: hidden;
   img{
     width: 100%;
     height: 100%;
   }
   ul{
     display: none;
     padding: 10%;
     width: 100%;
     max-height: 70%;
     overflow: hidden;
     list-style: none;
     position:absolute;
     top:50%;
     right:50%;
     transform: translate(50%, -50%);
     li{
       i{
         color: gray;
       }
       .yellowStar{
         color:yellow;
       }
       img{
         width: 25px;
       }
     }
   }
 } 
 .card:hover{
   background-color:$paragraph;
   img{
     display: none;
   }
   ul{
     color:black;
     display: flex;
     flex-direction: column;
     img{
       display: inline-block;
     }
   }
 }
</style>