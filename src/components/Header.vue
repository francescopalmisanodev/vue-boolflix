<template>
<header>
  <input type="search" placeholder="Cerca Film" name="film-bar" id="film-bar" v-model="searchString" @keyup.enter="$emit('search', searchString)">
  <button @click="$emit('search', searchString)">Cerca</button>
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

</style>