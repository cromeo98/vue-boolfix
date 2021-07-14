<template>
  <div>
      {{movieDetails.id}}
      {{movieDetails.original_title}}
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