<template>
  <div class="card">
    <div class="cover">
      <img :src="imgBaseURL + imgBaseDimension + serie.poster_path" :alt="'Copertina ' + serie.name">
    </div>
    Titolo = {{ serie.name }} <br>
    Titolo originale = {{ serie.original_name }} <br>
    Lingua = <img :src="getImgUrl(language)" v-bind:alt="language"> <br>
    Voto = {{ serie.vote_average }} <br>
  </div>
</template>

<script>
export default {
  name : 'CardSerieTv',
  props : ['serie', 'imgBaseURL', 'imgBaseDimension'],
  data(){
    return{
      language : this.serie.original_language
    }
  },
  methods : {
    getImgUrl(pic) {
      try {
        let fileName = require('../assets/img/' + pic + '.png');
        return fileName
      } 
      catch (none) {
        return 'none'
      }  
    }
  }
}
</script>

<style lang="scss">
  .card{
    width: 345.987px;
    height: 531.08px;
    margin-right: 20px;
    margin-bottom: 100px;
  }
  img {
    height: 15px;
  }

   .cover{
      img{
        height: 531px;
        width: 345.987px;
      }
    }
</style> 