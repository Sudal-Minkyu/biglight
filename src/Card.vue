<template>
    <div v-for="(roomData,i) in roomDetails" :key="i">
        <img @click="$emit('openModal', i); roomDetails[i].clickCnt++;" class="room-img" :src='roomDetails[i].image'> 
        <h4 @click="$emit('openModal', i); roomDetails[i].clickCnt++;">{{ roomDetails[i].title }}</h4>
        <p>내용 : {{roomDetails[i].content}}</p>
        <p>{{ roomDetails[i].state }}</p>
        <p v-if="roomDetails[i].startDate != null">
            기간 : {{roomDetails[i].startDate}} ~ {{roomDetails[i].endDate}}
        </p>
        <button type="button" class="btn btn-dark" style="margin: 5px;" @click="roomDetails[i].suggestion++">추천하기</button><span>추천수 : {{ roomDetails[i].suggestion }}</span>
    </div>
</template>

<script>
export default {
    name: 'Modal',
    props : {
        roomClickNum : Number,
        roomDetails : Array
    }
    
}
</script>

<style>
</style>