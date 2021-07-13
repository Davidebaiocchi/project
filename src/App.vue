<template>
  <div id="app">
    <Header @startTest="searchFilm"/>
    <Main :filmArray="filmArray" :searchText="searchText"/>
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import axios from 'axios';
export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return{
      apiURL : 'https://api.themoviedb.org/3/search/movie?',
      apiURLSerie : 'https://api.themoviedb.org/3/search/tv?',
      filmArray : [],
      searchText : ''
    }
  },
  methods : {
    searchFilm(inputText){
      // save user search text
      this.searchText = inputText;
      // call films API
      axios
        .get(this.apiURL, {
          params: {
            api_key : 'f019de624b3557ff30c3068e6b218a54',
            query : inputText,
            language : 'it-IT'
          }
        })
        .then(response => {
          this.filmArray = response.data.results;
          console.log(this.filmArray);
        })
        .catch((error) => {
          console.log('Errore : ' + error);
        });
    },
    searchSerie(inputText){
      // save user search text
      this.searchText = inputText;
      // call serie API
      axios
        .get(this.apiURLSerie, {
          params: {
            api_key : 'f019de624b3557ff30c3068e6b218a54',
            query : inputText,
            language : 'it-IT'
          }
        })
        .then(response => {
          this.filmArray = response.data.results;
          console.log(this.filmArray);
        })
        .catch((error) => {
          console.log('Errore : ' + error);
        });
    }
  }
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container{
  width: 100%;
  padding-left: 1px;
}
</style>