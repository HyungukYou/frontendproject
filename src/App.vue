<template>
  <div>

<!--    <div class="start" :class="{ end : 모달창열렸니 }">-->
    <transition name="fade">
      <Model @closeModel="모달창열렸니 = false" :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니"/>
    </transition>
<!--    </div>-->
    <div class="menu">
      <a v-for="a in 메뉴들" :key="a"> {{ a }}</a>
    </div>

    <Discount/>

    <Card @openModel="모달창열렸니 = true; 누른거 = i" :원룸="원룸들[i]" v-for="(작명,i) in 원룸들" :key="작명"/>
<!--    <Card :원룸="원룸들[1]"/>-->
<!--    <Card :원룸="원룸들[2]"/>-->
<!--    <Card :원룸="원룸들[3]"/>-->
<!--    <Card :원룸="원룸들[4]"/>-->
<!--    <Card :원룸="원룸들[5]"/>-->


<!--    <div>
      {{logo}}
      <img :src="원룸들[0].image" class="room-img">
      <h4>{{원룸들[0].title}}</h4>
      <p>{{ 원룸들[0].price}} 만원</p>
      <button @click="increase">허위매물신고</button> <span> 신고수 : {{신고수[0]}} </span>
    </div>
    <div>
      <img :src="원룸들[1].image" class="room-img">
      <h4>{{ 원룸들[1].title }}</h4>
      <p>{{ 원룸들[1].price }} 만원</p>
    </div>
    <div>
      <img :src="원룸들[2].image" class="room-img">
      <h4>{{ 원룸들[2].title}}</h4>
      <p>{{ 원룸들[2].price }} 만원</p>
    </div>
    <div>
      <img :src="원룸들[3].image" class="room-img">
      <h4>{{ 원룸들[3].title}}</h4>
      <p>{{ 원룸들[3].price }} 만원</p>
    </div>
    <div>
      <img :src="원룸들[4].image" class="room-img">
      <h4>{{ 원룸들[4].title}}</h4>
      <p>{{ 원룸들[4].price }} 만원</p>
    </div>
    <div>
      <img :src="원룸들[5].image" class="room-img">
      <h4>{{ 원룸들[5].title}}</h4>
      <p>{{ 원룸들[5].price }} 만원</p>
    </div>
    <div v-for="(a,i) in 원룸들" :key="i">
      <img :src="a.image" class="room-img">
      <h4 @click="모달창열렸니 = true; 누른거 = i ">{{ a.title}}</h4>
      <p>{{ a.price }} 만원</p>
    </div>-->
  </div>
</template>

<script>
  import Discount from "@/Discount";
  var array = [10,20,30];
  array[0]

  import data from './assets/oneroom.js';
  import Model from "@/Model";
  import Card from "@/Card";

export default {
  name: 'App',
  data(){ // 데이터 보관
    return{
      오브젝트 : {name : 'kim' , age:20},
      누른거 : 0,
      원룸들 : data,
      모달창열렸니 : false,
      신고수 : [0,0,0],
      price1 : 60, // 자료 이름 , 자료 내
      price2 : 70,
      price3 : 80,
      logo : '원룸샵',
      스타일 : 'color :blue',
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      메뉴들 : ['Home','Shop','About'],
    }
  },
  methods : {
    increase(){
      this.신고수 +=1;
    }
  },
  components: {
    Model,
    Discount,
    Card,
  }
}
</script>

<style>
.fade-leave-from{
  opacity: 1;
}
.fade-leave-active{
  transition: all 1s;
}
.fade-leave-to{
  opacity: 0;
}
.fade-enter-from{
  opacity: 0;
}
.fade-enter-active{
  transition: all 1s;
}
.fade-enter-to{
  opacity: 1;
}
.start {
  opacity: 0;
  transition: all 1s;
}
.end {
  opacity: 1;
}
body {
  margin: 0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
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
