<template>
<header>
  <h2>Boolflix</h2>
  <section>
    <input type="search" placeholder="Cerca Film" name="film-bar" id="film-bar" v-model="searchString" @keyup.enter="$emit('search', searchString)">
    <span @click="$emit('search', searchString)"><i class="fa-solid fa-magnifying-glass"></i></span>
  </section>
</header>
</template>

<script>

export default {
    name:"Header",
    data(){
      return {
        searchString:"",
      }
    }  
}
</script>

<style lang="scss">
@import "../scss/variables.scss";
  header {
    margin: 20px;
    display: flex;
    justify-content: space-between;
    input{
      background-color:$paragraph;
      color:#001e1d ;
      border:0px;
      border-radius:3px;
      height: 20px;
      margin-right: 10px;
      width: 170px;
      padding: 5px;
    }
    span{
      i{
        color: $paragraph;
        font-size: 18px;
      }
    }
  }
</style>