<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->

  <div class="black-bg" v-if="modalbool == true">
    <div class="white-bg">
        <img class="room-img" :src='roomDetails[roomClickNum].image'> 
        <h4>{{ roomDetails[roomClickNum].title }}</h4>
        <p>내용 : {{ roomDetails[roomClickNum].content }}</p>
        <p>조회수 : {{ roomDetails[roomClickNum].clickCnt }}</p>
        <button @click = "modalbool = false">닫기</button>
    </div>
  </div>

  <h1>큰빛빌라</h1>
  <div class="menu">
    <a v-for="menuName in menuLists" :key="menuName" >{{ menuName }}</a>
  </div>

  <div v-for="(roomData,i) in roomDetails" :key="i">
    <img @click = "modalbool = true; roomDetails[i].clickCnt++; roomClickNum = i" class="room-img" :src='roomDetails[i].image'> 
    <h4 @click = "modalbool = true; roomDetails[i].clickCnt++; roomClickNum = i">{{ roomDetails[i].title }}</h4>
    <p>내용 : {{roomDetails[i].content}}</p>
    <p>{{ roomDetails[i].state }}</p>
    <p v-if="roomDetails[i].startDate != null">
      기간 : {{roomDetails[i].startDate}} ~ {{roomDetails[i].endDate}}
    </p>
    <button @click="roomDetails[i].suggestion++">추천하기</button><span>추천수 : {{ roomDetails[i].suggestion }}</span>
  </div>

</template>

<script>

import roomData from './assets/room';

export default {
  name: 'App',
   data(){
    return {
      modalbool : false,
      menuLists : ['Home', 'Room', 'About'],
      roomDetails : roomData,
      roomClickNum : 0,
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
