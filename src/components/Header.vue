<template>
  <header class="lead py-3">
    <h3 class="ps-3">BoolFix</h3>
    <!-- qui andrà inserito anche il logo -->

    <input type="text" name="search-movie" id="search-movie" placeholder="Cerca un film o una serie tv" v-model="search" @keyup="$emit('research', search)">

    <button type="button" class="btn btn-outline-primary">Primary</button>
  </header>
</template>

<script>
export default {
  name: 'Header',
  data (){
    return {
      search: ''
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  header{
    background-color: black;
      h3{
        color: red;
      }
  }
</style>
