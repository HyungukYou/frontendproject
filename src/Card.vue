<template>
  <div>
    <div>
      <img :src="원룸.image" class="room-img">
      <h4 @click="$emit('openModel', 원룸.id)">{{원룸.title}}</h4>
      <p>{{원룸.price }} 만원</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props : {
    원룸 : Object,
  },
  methods : {
    함수(){

    }
  }
}
</script>

<style>

</style>