<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <div class="black-bg" v-if="modalbool == true">
    <div class="white-bg">
      <h4>상세페이지제목임</h4>
      <p>상세페이지내용임</p>
      <button @click = "modalbool = false">닫기</button>
    </div>
  </div>
  <h1>큰빛빌라</h1>
  <div class="menu">
    <a v-for="menuName in menuLists" :key="menuName" >{{ menuName }}</a>
  </div>

  <div v-for="(roomName,i) in roomLists" :key="i">
    <img @click = "modalbool = true" class="room-img" src='./assets/room0.jpg'> 
    <h4>{{ roomLists[i] }}</h4>
    <p>{{ states[i] }}</p>
    <p v-if="startDate[i] != null">기간 : {{startDate[i]}} ~ {{endDate[i]}}</p>
    <button @click="suggestion[i]++">추천하기</button><span>추천수 : {{ suggestion[i] }}</span>
  </div>

</template>

<script>

export default {
  name: 'App',
   data(){
    return {
      modalbool : false,
      imagesLists : [
        './assets/room0.jpg','./assets/room1.jpg','./assets/room2.jpg','./assets/room3.jpg','./assets/room4.jpg'
      ],
      menuLists : ['Home', 'Room', 'About'],
      roomLists : ['101호', '102호', '103호', '103호', '105호'],
      states : ['계약중', '계약중', '빈방', '빈방', '계약중'],
      suggestion : [0, 0, 0, 0, 0],
      startDate : ['2022-05-10', '2022-01-01', null, null, '2022-03-10'],
      endDate : ['2023-01-01', '2022-12-10', null, null, '2022-10-03'],
    }
  },

  methods : {
    
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

.room-img {
  width: 100%;
  margin-top: 40px;
}

body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
} 

</style>
