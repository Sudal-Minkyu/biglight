<template>
  <div class="black-bg" v-if="modalbool == true">
    <div class="white-bg">
        <h2>큰빛빌라 {{ roomDetails[roomClickNum].title }}</h2>
        <img class="room-img" :src='roomDetails[roomClickNum].image'> 
        <!-- <input style="text-align: center;" v-model="message" />
        <p>인사 : {{message}}</p> -->
        <p>내용 : {{ roomDetails[roomClickNum].content }}</p>
        <p>조회수 : {{ roomDetails[roomClickNum].clickCnt }}</p>
        <button @click = "$emit('closeModal')">닫기</button>
    </div> 
  </div>
</template>

<script>
export default {
    name: 'Modal',
    data(){
        return{
            // message : ''
        }
    },
    watch :{
        // watch : 함수명은 데이터명과 동일하게 작성해야한다.
        // message(text){
        //   console.log(text);
        // }
    },
    props : {
        roomClickNum : Number,
        roomDetails : Array,
        modalbool : Boolean
    }
}
</script>

<style>
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