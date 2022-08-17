<template>

  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <Discount></Discount> -->

  <!-- <div class="start" :class="{end : modalbool}"> -->
  <transition name="fade">
    <Modal 
      @closeModal="modalbool = false;" 
      :roomDetails="roomDetails" :modalbool="modalbool" :roomClickNum="roomClickNum">
    </Modal>
  </transition>
  <!-- </div> -->

  <h1>큰빛빌라</h1>
  <div class="menu">
    <a v-for="menuName in menuLists" :key="menuName" >{{ menuName }}</a>
  </div>

  <Card 
    @openModal="modalbool = true; roomClickNum = $event"
    :roomDetails="roomDetails" :roomClickNum="roomClickNum">
  </Card>

</template>

<script>

import roomData from './assets/room';
// import Discount from './Discount.vue'
import Modal from './Modal.vue'
import Card from './Card.vue'

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
    // Discount: Discount,
    Modal: Modal,
    Card: Card
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
body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}

/* 닫기 애니메이션 */
.fade-leave-from{
  /* 시작 */
  opacity: 1;
}
.fade-leave-active{
  transition: all 1s;
}
.fade-leave-to{
  /* 끝 */
  opacity: 0;
}

/* 열기 애니메이션 */
.fade-enter-from{
  /* 시작 */
  transform: translateY(-100px);
  opacity: 0;
}
.fade-enter-active{
  transition: all 1s;
}
.fade-enter-to{
  /* 끝 */
  transform: translateY(0px);
  opacity: 1;
}

</style>
