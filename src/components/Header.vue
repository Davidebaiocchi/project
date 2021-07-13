<template>
  <header>
    <div class="left-section">
      <h1>
        Boolflix
      </h1>
    </div>

    <div class="right-section">
      <form action="">
        <input 
        type="text" 
        v-model.trim="srcText">
        <button @click.prevent="$emit('startTest',srcText)">Cerca</button>
      </form>
    </div>
  </header>
</template>

<script>
export default {
  name : 'Header',
  data(){
    return{
      srcText : ''
    }
  }
}
</script>

<style lang="scss">
  header{
    position: fixed;
    display: flex;
    width: 100%;
    justify-content: space-between;
    align-items: center;
    background-color: #0d0d0d;
    height: 80px;
    padding: 0 20px;
    .left-section{
      color: red;
      font-size: 25px;
    }
    .right-section{
      form{
        *{
          height: 40px;
          margin-right: 20px;
          cursor: pointer;
        }
        input {
          width: 200px;
          padding-left: 10px;
          font-size: 18px;
        }
      }
    }
  }
</style>