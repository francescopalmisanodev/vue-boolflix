<template>
  <div class="card">
    <ul>
      <li>Titolo del Film: {{title}}</li>
      <li>Titolo originale del Film: {{orgTitle}}</li>
      <li>Lingua del Film: <img v-if="Flags.includes(language)" :src="require(`@/boolflix-flags/${language}.png`)" :alt="language">
      <span v-else>{{language}}</span>
      </li>
      <li>Voto del Film: {{vote}}</li>
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
    }
}
</script>

<style lang="scss">
 .card{
   li{
     img{
       width: 20px;
     }
   }
 } 
</style>