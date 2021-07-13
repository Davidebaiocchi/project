<template>
  <main>
    <div class="container">

      <div class="Cards">

        <Card 
        v-for="(film,i) in filmArray"
        :key="i"
        :film="film"/>

      </div>
    </div>
  </main>
</template>

<script>
import Card from '@/components/Card.vue';
export default {
  name : 'Main',
  components : {
    Card
  },
  props : ['searchText', 'filmArray']
}
</script>

<style lang="scss">
  main{
    padding: 30px 0;
    height: 100vh;
    overflow-y: scroll;
    padding-top: 80px;
    background-color: #141414;
    color: white;
    .Cards{
      margin-top: 50px;
      display: flex;
      align-items: flex-start;
      flex-wrap: wrap;
      padding-left: 150px;
    }
  }
</style>
