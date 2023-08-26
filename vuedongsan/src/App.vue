
<template>

  <div class="black-bg" v-if="모달창열렸[i]">
    <div class="white-bg">
      <h4>원룸들[i].title</h4>
      <p>원룸들[i].content</p>
      <button @click="모달창열렸[i]=false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="a in menus" :key="a">{{ a }}</a>
    <!-- key = unigue key -->
  </div>

  <!-- 모달창 겉에까맣고 안에 하얗고-->




  <!-- <div v-for="(b, i) in 3" :key="i">
    <h4> {{ products[i] }}</h4>
    <p> {{ price[i] }}</p>
  </div> -->

  <div v-for="(b, i) in 3" :key="i">
    <img :src="원룸들[i].image" class="room-img">
    <h4 @click="모달창열렸[i]=true">{{ 원룸들[i].title }}</h4>
    <p>{{ 원룸들[i].price }} 원</p>
    <!-- <button @click="increase(0)">허위매물신고</button><span>신고수 : {{ 신고수[0] }}</span> -->
    <!-- <button @mouseover="신고수++">허위매물신고</button><span>신고수 : {{ 신고수 }}</span> -->
    <!-- <button v-on:click="자바스크립트">허위매물신고</button><span>신고수 : 0</span> -->
  </div>

</template>

<script>

// {{데이터바인딩}} 하는 이유 : Vue의 실시간 자동 렌더링. 웹앱

// import 작명 from './assets/oneroom.js';
// import {apple, apple2} from './assets/oneroom.js';
import data from './assets/oneroom';

export default {
  name: 'App',
  data() {
    return {
      // 데이터 보관함 object 자료
      원룸들 : data,
      모달창열렸 : [false, false, false],
      신고수 : [0, 0, 0],
      menus : ['Home', 'Product', 'About'],
      price : [60, 70, 80],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods : {
    increase(i) {
      this.신고수[i]++;
    }
  },
  components: {
  }
}
</script>

<style>

body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
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
  /* margin-top: 60px; */
}
.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
</style>
