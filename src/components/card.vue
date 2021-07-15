<template>
  <div>
      <ul>
          <li>Titolo: {{details.title || details.name}}</li> 
          <!-- OR <li>Titolo: {{!details.title ? details.name : details.title}}</li>  -->
          <li>Titolo originale: {{details.original_title || details.original_name}}</li>
          <li>Voto: {{details.vote_average}}</li>
          <li>Lingua: {{details.original_language}}</li>
      </ul>    
  </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        details: Object
    }
}
</script>

<style>

</style>