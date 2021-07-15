<template>
  <div>
      <ul>
          <li>Titolo: {{details.title || details.name}}</li> 
          <!-- OR <li>Titolo: {{!details.title ? details.name : details.title}}</li>  -->
          <li>Titolo originale: {{details.original_title || details.original_name}}</li>
          <li>Voto: {{details.vote_average}}</li>
          <li v-if="!flags.includes(details.original_language)">
              Lingua: {{details.original_language}}
          </li>
          <li v-else>
              Lingua: 
              <img :src="
                        require(`../assets/${details.original_language}.png`)
                       " 
                   :alt="`${details.original_language} flag`">
          </li>
      </ul>    
  </div>
</template>

<script>
export default {
    name: 'Card',
    data(){
        return{
            flags: ['en', 'it']
        }
    },
    props: {
        details: Object
    }
}
</script>

<style scoped lang="scss">

li{
    img{
        width: 15px;
    }
}

</style>