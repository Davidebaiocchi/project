<template>
  <div class="card">
    Titolo = {{film.title}} <br>
    Titolo originale = {{film.original_title}} <br>
    Lingua = {{film.original_language}} <br>
    Voto = {{film.vote_average}} <br>
  </div>
</template>

<script>
export default {
  name : 'Card',
  props : ['film']
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
</style>