<template>
  <div id="app">

    <div class="black-bg" v-if="openModal == true">
      <div class="white-bg">
        <h4>상세 페이지</h4>
        <p>상세 페이지 내용</p>
        <button @click="openModal = false">닫기</button>
      </div>
    </div>

    <div class="menu">
      <a v-for="a in menus" :key="a">{{a}}</a>
    </div>

    <div>
      <img :src="onerooms[0].image" class="room-img" @click="openModal = true">
      <h4>{{ onerooms[0].title }}</h4>
      <p>{{ onerooms[0].price }}원</p>
    </div>
    <div>
      <img src="./assets/room1.jpg" class="room-img">
      <h4>{{ products[1] }}</h4>
      <p>60 만원</p>
      <button @click="report[1] += 1">허위 매물 신고</button> <span>신고 수: {{report[1]}}</span>
    </div>
    <div>
      <img src="./assets/room2.jpg" class="room-img">
      <h4>{{ products[2] }}</h4>
      <p>70 만원</p>
      <button @click="report[2] += 1">허위 매물 신고</button> <span>신고 수: {{report[2]}}</span>
    </div>
  </div>
</template>

<script>

import data from './components/oneroom.js';

export default {
  name: 'App',
  data() {
    return {
      onerooms: data,
      openModal: false,
      report: [0, 0, 0],
      menus: ['Home', 'Shop', 'About'],
      products: ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  methods: {
    increase() {
      this.report += 1;
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
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.room-img {
  width: 100%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
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
</style>