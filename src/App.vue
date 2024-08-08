<template>
  <div id="app">

    <div class="menu">
      <a v-for="a in menus" :key="a">{{a}}</a>
    </div>
    <div>
      <img src="./assets/room0.jpg" class="room-img">
      <h4>{{ products[0] }}</h4>
      <p>50 만원</p>
      <button @click="report[0] += 1">허위 매물 신고</button> <span>신고 수: {{report[0]}}</span>
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

export default {
  name: 'App',
  data() {
    return {
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