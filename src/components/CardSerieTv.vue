<template>
  <div class="card">
    <div class="cover">
      <img :src="imgBaseURL + imgBaseDimension + serie.poster_path" :alt="'Copertina ' + serie.name">
    </div>
    <div class="description">
      Titolo = {{ serie.name }} <br>
      Titolo originale = {{ serie.original_name }} <br>
      Lingua = <img :src="getImgUrl(language)" v-bind:alt="language"> <br>
      Voto = {{ serie.vote_average }} <br>
    </div>
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
    width: 300px;
    margin-right: 10px;
    height: 500px;
    margin-bottom: 100px;
    position: relative;
  }
  img {
    height: 15px;
  }

  .cover{
    img{
      height: 500px;
      width: 300px;
    }
  }

  .description {
    // position: relative;
    // bottom: 280px;
    // left: 80px;
    position: absolute;
    top: 50%;
    left: 50%;
    z-index: 1;
  }
</style> 