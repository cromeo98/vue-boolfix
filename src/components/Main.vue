<template>
  <section id="jumbo">
    <input type="text" name="search-movie" id="search-movie">
    <button type="button" class="btn btn-outline-primary">Primary</button>
  </section>
</template>

<script>
import axios from "axios";

export default {
    name: "Main",
    data () {
        return {
          apiURL: 'https://api.themoviedb.org/3/search/movie?api_key=d2e20f2e9286826809356fcd801cdf54&query=matrix',
          movieList: []
        }
    },
    created(){
      this.getMovies();
    },
    methods: {
      getMovies(){
        axios
          .get(this.apiURL)
          .then(res => {
            this.movieList = res.data;
            console.log(this.movieList);
          })
      }
    }
}

</script>

<style scoped lang="scss">

</style>