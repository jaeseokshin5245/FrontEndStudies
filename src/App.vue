<template>
  <div class="black-bg" v-if="modal_stat == true">
    <div class="white-bg">
      <h4>상세페이지</h4>
      <h5>상세페이지 내용</h5>
      <button @click="modal_stat=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="menubar in menubars" :key="menubar">{{ menubar }}</a>
  </div>

  <div v-for ="asdf in roomsInfos" :key="asdf.id" class="room_id">
    <img :src= "asdf.image" class="room-img" />
    <h4 @click="modal_stat=true">{{ asdf.title }}</h4>
    <p>{{ asdf.price }}</p>
    <p>{{ asdf.content }}</p>
  </div>

</template>

<script>

import data from './assets/data.js';
data 
export default {
  name: 'App',
  data(){
    return{
      roomsInfos : data,
      modal_stat : false,
      count : [0,0,0],
      menubars : ["Home", "Shop", "About"],
      priceOne : 60,
      priceTwo : 100,
      priceThree : 120,
      products : ['역삼동 원룸', '천호동 원룸', '마포구 원룸']
    }
  },
  components: {
  }
}
</script>

<style>
body{
  margin: 0;
}

div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.room-img{
  width: 50%;
  padding: 20px;
}
</style>
