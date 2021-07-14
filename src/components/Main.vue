<template>
  <main>
    <div class="container">
      <div class="search-movie-serie-tv">

      </div>
      <Card v-for="searchedMovie in searchedMovies" :key="searchedMovie.id"/>
    </div>
  </main>
</template>

<script>
import Card from '@/components/card.vue'

export default {
  name: "Main",
  components: {
    Card
  },
  props: {
    searchedMovies: Array
  }
}

</script>

<style scoped lang="scss">

</style>