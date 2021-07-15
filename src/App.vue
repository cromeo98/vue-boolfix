<template>
  <div id="app">
    <Header @research="researchMovieOrTv"/>
    <Main :searchedMovies="searchedMovies" :searchedTvSeries="searchedTvSeries" :searched="youSearched"/>
  </div>
</template>

<script>
import axios from "axios";
import Header from '@/components/Header.vue';
import Main from '@/components/Main.vue';


export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data () {
    return {
      movieUrl: "https://api.themoviedb.org/3/search/movie",
      tvSeriesUrl: "https://api.themoviedb.org/3/search/tv",
      apiKey: "d2e20f2e9286826809356fcd801cdf54",
      language: "it-IT",
      searchedMovies: [],
      searchedTvSeries: [],
      youSearched: ''
    }
  },
  methods: {
    researchMovieOrTv(input){
      this.youSearched = input
      const request = {
          params:{
            api_key: this.apiKey,
            language: this.language,
            query: input
          }
      }
      axios
        .all([
          axios.get(this.movieUrl, request),
          axios.get(this.tvSeriesUrl, request)
        ])
        .then(axios.spread((responseMovie, responseTvSeries) => {
          this.searchedMovies = responseMovie.data.results;
          this.searchedTvSeries = responseTvSeries.data.results;
        }))
    }
  }
}
</script>

<style lang="scss">

@import "@/style/general.scss";

</style>
