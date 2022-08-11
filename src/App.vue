<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div id='roomList'>
    <div>
      <p>{{ products[0] }}</p>
      <p>{{ states[0] }}</p>
    </div>
    <div>
      <p>{{ products[1] }}</p>
      <p>{{ states[1] }}</p>
    </div>
    <div>
      <p>{{ products[2] }}</p>
      <p>{{ states[2] }}</p> 
    </div>
    <div>
      <p>{{ products[3] }}</p>
      <p>{{ states[3] }}</p> 
    </div>
    <div>
      <p>{{ products[4] }}</p>
      <p>{{ states[4] }}</p> 
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
   data(){
    return {
      products : ['101호', '102호', '103호', '103호', '105호'],
      states : ['계약중', '계약중', '빈방', '빈방', '계약중'],
    }
  },
  components: {

  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
