<template>
  <main>
    <div class="container">
      <div class="search-movie-serie-tv">

      </div>
      <Card v-for="searchedMovie in searchedMovies" :key="searchedMovie.id" :movieDetails="searchedMovie"/>
    </div>
  </main>
</template>

<script>
import Card from '@/components/Card.vue'

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