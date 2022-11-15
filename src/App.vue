<template>
  <div class="black-bg" v-if="modalOpen == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="modalOpen = false">닫기</button>
    </div>
  </div>
  <div class="menu">
    <a v-for="top in topmenus" :key="top">{{ top }}</a>
  </div>
  <!-- <div v-for="(house, i) in products" :key="i">
    <h4>{{ house }}</h4>
    <p>50 만원</p>
  </div> -->
  <div>
    <img src="./assets/room0.jpg" class="roomImg" />
    <h4 @click="modalOpen = true">{{ products[0].title }}</h4>
    <p>{{ products[0].price }}원</p>
    <button v-on:click="increase">허위매물신고</button>
    <span>신고 수 : {{ reportedNumber1 }}</span>
  </div>
  <div>
    <img :src="products[1].image" class="roomImg" />
    <h4 @click="modalOpen = true">{{ products[1].title }}</h4>
    <p>{{ products[1].price }}원</p>
    <button v-on:click="increase2">허위매물신고</button>
    <span>신고 수 : {{ reportedNumber2 }}</span>
  </div>
  <div>
    <img :src="products[2].image" class="roomImg" />
    <h4 @click="modalOpen = true">{{ products[2].title }}</h4>
    <p>{{ products[2].price }}원</p>
    <button v-on:click="increase3">허위매물신고</button>
    <span>신고 수 : {{ reportedNumber3 }}</span>
  </div>
  <div>
    <img :src="products[3].image" class="roomImg" />
    <h4 @click="modalOpen = true">{{ products[3].title }}</h4>
    <p>{{ products[3].price }}원</p>
  </div>
  <div>
    <img :src="products[4].image" class="roomImg" />
    <h4 @click="modalOpen = true">{{ products[4].title }}</h4>
    <p>{{ products[4].price }}원</p>
  </div>
  <div>
    <img :src="products[5].image" class="roomImg" />
    <h4 @click="modalOpen = true">{{ products[5].title }}</h4>
    <p>{{ products[5].price }}원</p>
  </div>
</template>

<script>
import data from "./data/post.js";

export default {
  name: "App",
  data() {
    return {
      modalOpen: false,
      reportedNumber1: 0,
      reportedNumber2: 0,
      reportedNumber3: 0,
      topmenus: ["Home", "Shop", "About"],
      // products: ["역삼동원룸", "천호동원륨", "마포구원룸"],
      products: data,
    };
  },
  methods: {
    increase() {
      this.reportedNumber1 += 1;
    },
    increase2() {
      this.reportedNumber2 += 1;
    },
    increase3() {
      this.reportedNumber3 += 1;
    },
  },
  components: {},
};
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

.roomImg {
  width: 100%;
  margin-top: 40px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
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
