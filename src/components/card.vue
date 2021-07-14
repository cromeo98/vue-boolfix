<template>
  <div>
      {{movieDetails.title}}
      {{movieDetails.original_title}}
      {{movieDetails.vote_average}}
      {{movieDetails.original_language}}
  </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        movieDetails: Object
    }
}
</script>

<style>

</style>