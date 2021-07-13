<template>
  <div class="card">
    Titolo = {{film.title}} <br>
    Titolo originale = {{film.original_title}} <br>
    Lingua = <img :src="getImgUrl(language)" v-bind:alt="language"> <br>
    Voto = {{film.vote_average}} <br>
  </div>
</template>

<script>
export default {
  name : 'Card',
  props : ['film'],
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
      catch (i) {
        return 'none'
      }  
    }
  }
}
</script>

<style lang="scss">
  .card{
    width: calc(100% / 9);
    background-color: rgb(34, 0, 128);
    border: 1px solid rgb(255, 255, 255);
    padding: 20px;
    height: 300px;
    margin-right: 5px;
    margin-bottom: 40px;
  }
  img {
    height: 15px;
  }
</style>