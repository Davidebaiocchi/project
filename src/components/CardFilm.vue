<template>
  <div class="card">
    <div class="cover">
      <img :src="imgBaseURL + imgBaseDimension + film.backdrop_path" :alt="'Copertina ' + film.title">
    </div>
    Titolo = {{film.title}} <br>
    Titolo originale = {{film.original_title}} <br>
    Lingua = <img :src="getImgUrl(language)" v-bind:alt="language"> <br>
    Voto = {{film.vote_average}} <br>
  </div>
</template>

<script>
export default {
  name : 'CardFilm',
  props : ['film','imgBaseURL','imgBaseDimension'],
  data(){
    return {
      language: this.film.original_language
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
    width: 380.987px;
    height: 300px;
    margin-right: 5px;
    margin-bottom: 40px;
  }
  img {
    height: 15px;
  }
  .cover{
      img{
        height: 380px;
        width: 345.987px;
      }
    }
</style>