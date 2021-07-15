<template>
  <main>
    <div class="container">
      <div class="search-movie-serie-tv">

        <h4>Hai cercato: {{searched}}</h4>

      </div>
      <div>
        <h4>Films</h4>
        <Card v-for="searchedMovie in searchedMovies" :key="searchedMovie.id" :details="searchedMovie"/>
      </div>
      <div>
        <h4>SerieTV</h4>
        <Card v-for="searchedTvSeries in searchedTvSeries" :key="searchedTvSeries.id" :details="searchedTvSeries"/>
      </div>

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
    searchedMovies: Array,
    searchedTvSeries: Array,
    searched: String
  }
}

</script>

<style scoped lang="scss">

</style>