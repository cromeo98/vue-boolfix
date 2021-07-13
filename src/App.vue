<template>
  <div id="app">
    <Header msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'


export default {
  name: 'App',
  components: {
    Header
  }
}
</script>

<style lang="scss">

@import "@/style/general.scss"

</style>
