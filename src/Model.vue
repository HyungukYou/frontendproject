<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <input v-model="month">
      <input type="range" min="1" max="12">
<!--      <input type="checkbox" v-model="month">-->
<!--      <input @input="month = $event.target.value">-->
      <select v-model="month">
        <option>1</option>
        <option>3</option>
        <option>6</option>
        <option>12</option>
      </select>
      <p>{{ 원룸들[누른거].content }}</p>
      <p> {{ month }}개월 선택함 : {{ 원룸들[누른거].price * month }}</p>
      <button @click="$emit('closeModel')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Model',
  data(){
    return{
      month : 1,
    }
  },
  // watch : {
  //   month(a) {
  //     if (a >= 13){
  //       alert('13이상 입력하지 마셈')
  //     }
  //   }
  // },
  watch : {
    month(b){
      if (isNaN(b) == true){
        alert('문자입력하지마라');
        this.month = 1;
      }
    },
  },
  props : {
    원룸들 : Array,
    누른거 : Number,
    모달창열렸니 : Boolean,
  }
}
</script>

<style>

</style>