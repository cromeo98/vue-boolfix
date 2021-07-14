<template>
  <div id="app">
    <Header @research="researchMovieOrTv"/>
    <Main/>
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
      apiUrl: "https://api.themoviedb.org/3/search/movie",
      apiKey: "d2e20f2e9286826809356fcd801cdf54",
      language: "it-IT"
    }
  },
  methods: {
    researchMovieOrTv(input){
      axios
        .get(this.apiUrl, {
          params:{
            api_key: this.apiKey,
            language: this.language,
            query: input
          }
        })
        .then( response => {
          console.log(response);
        })
    }
  }
}
</script>

<style lang="scss">

@import "@/style/general.scss";

</style>
