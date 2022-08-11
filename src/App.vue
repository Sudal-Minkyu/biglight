<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->

  <div class="menu">
    <a v-for="menuName in menuLists" :key="menuName" >{{ menuName }}</a>
  </div>

  <div v-for="(roomName,i) in roomLists" :key="i">
    <p>{{ roomLists[i] }}</p>
    <p>{{ states[i] }}</p>
  </div>

</template>

<script>

export default {
  name: 'App',
   data(){
    return {
      menuLists : ['Home', 'Room', 'About'],
      roomLists : ['101호', '102호', '103호', '103호', '105호'],
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
}

.menu {
  background : darkslateblue;
  padding : 15px;
  border-radius : 5px;
}
.menu a {
  color : white;
  padding : 10px;
}

</style>
