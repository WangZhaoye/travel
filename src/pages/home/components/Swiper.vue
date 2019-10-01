<template>
<div class="wrapper">
  <swiper :options="swiperOption" v-if="list.length">
    <swiper-slide v-for="item of list" :key="item.id">
      <img class="img-swiper" 
      :src="item.imgUrl"/>
    </swiper-slide>

    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
</div>
  
</template>

<script>
export default {
  name: "HomeSwiper",
  props: {
    list: Array
  },
  data(){
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true,
        autoplay: true,
        speed: 3000,
        //effect: "flip"
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff !important
  .wrapper
    overflow: hidden
    width: 100%
    height:0
    padding-bottom: 29%
    background: #eee
    .img-swiper
      width: 100%
    
 

</style>