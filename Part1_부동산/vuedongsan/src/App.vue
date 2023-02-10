<template>
  <!-- <div class="menu">
    <a>HOME</a>
    <a>PRODUCTS</a>
    <a>ABOUT</a>
  </div> -->

  <div class="menu">
    <a v-for="a in menuBar" :key="a">{{ a }}</a>
  </div>

  <!-- 모달창 -->
  <div v-if="modal_status == true">
    <div class="modal-black">
      <div class="modal-white">
          <h4>상세페이지</h4>
          <p>내용</p>
          <button @click="modal_status=false">X</button>
      </div>
    </div>
  </div>
  <img alt="Vue logo" src="./assets/logo.png">
  
 
  <!-- <div>
    <h3>{{ products[0] }}</h3>
    <h5>{{ prices[0] }}</h5>
  </div>
  <div>
    <h3>{{ products[1] }}</h3>
    <h5>{{ prices[1] }}</h5>
  </div>
  <div>
    <h3>{{ products[2] }}</h3>
    <h5>{{ prices[2] }}</h5> -->
  <!-- </div> -->


  <!-- 반복문 사용으로 내용 줄이기 -->

  <!-- <div v-for="(a, i) in products" :key="i">
    <h3>{{ products[i] }}</h3>
    <h5>{{ prices[i] }}</h5>
  </div> -->


  <!-- 버튼, 이미지 넣기-->
  <!-- <div v-for="(a, i) in names" :key="i" @click="modal_status = true">
    <img src="./assets/Cat.jpg" class="animal-img">
    <h3>{{ names[i] }}</h3>
    <h5>도력 : {{ power[i] }}</h5>
    <button @click="reportCount[i]++">좋아요</button> <span><span style="color: red">&#10084;</span>{{reportCount[i]}}</span>
  </div> -->

  <div v-for="(a, i) in animals" :key="i">
    <img src="#">
    <h4>{{ animals[i].title }}</h4>
    <h4>{{ animals[i].content }}</h4>
    <h4>도력 : {{ animals[i].power}}</h4>
  </div>

</template>


<script>
import cat from './data.js';

export default {
  name: 'App',
  data() {
    return {
      names : ['역삼동호랑이', '천호동타이거', '마포불주먹'],
      power : ['500', '1000', '2000'],
      menuBar : ['HOME', 'SHOP', 'ABOUT'],
      reportCount : [0,0,0],
      modal_status: false,
      animals : cat,
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

.animal-img {
  width: 50%;
  margin-top: 40px;
}

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.modal-black {
  width: 100%;
  height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}

.modal-white {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 50px;
}
</style>
