<template>
  <div>
      <ul>

          <img :src="`${coverUrl}${coverSize}${details.poster_path}`" 
          :alt="details.title || details.name"> 
          <li>Titolo: {{details.title || details.name}}</li>       
          <!-- OR <li>Titolo: {{!details.title ? details.name : details.title}}</li>  -->
          <li>Titolo originale: {{details.original_title || details.original_name}}</li>
          <li>Voto: {{changeVoteInOneToFive(details.vote_average)}}</li>
          <li v-if="!flags.includes(details.original_language)">
              Lingua: {{details.original_language}}
          </li>
          <li v-else>
              Lingua: 
              <img class="lang-flag" :src="
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
            flags: ['en', 'it'],
            coverSize: 'w185',
            coverUrl: 'https://image.tmdb.org/t/p/'
        }
    },
    methods: {
        changeVoteInOneToFive(data){
            let oneToFive = data / 2;
            return oneToFive.toFixed(0);
        }
    },
    props: {
        details: Object
    }
}
</script>

<style scoped lang="scss">

.lang-flag{
        width: 15px;
    }

</style>