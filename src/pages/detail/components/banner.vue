<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p18/201211/03/db9f2bb27ee40bf893835fbb.jpg_600x330_9bbb7595.jpg" />
      <div class="banner-info">
        <div class="banner-title">美龄宫</div>
        <div class="banner-number">
          <span class="banner-icon iconfont arrow-icon">&#xe69f;</span>
          2
        </div>
      </div>
    </div>
    <common-gallary 
      :imgs="imgs" 
      v-show="showGallary" 
      @close="handleGallaryClick">
    </common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  data(){
    return{
      showGallary: false,
      imgs:["//img1.qunarzz.com/sight/p18/201211/03/db9f2bb27ee40bf893835fbb.jpg_600x330_9bbb7595.jpg",
        "http://img1.qunarzz.com/sight/p0/1604/f7/f734c9db196a2af090.water.jpg_350x240_07c938ab.jpg"]
    }
  },
  components:{
    CommonGallary
  },
  methods:{
    handleBannerClick(){
      this.showGallary = true
    },
    handleGallaryClick(){
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      width: 100%
    .banner-info
      display: flex
      position: absolute 
      left: 0
      right: 0
      bottom: 0
      color: #fff
      line-height: .6rem
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
      .banner-title
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        padding: 0 .4rem
        border-radius: .2rem
        background: rgba(0, 0, 0, .8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
