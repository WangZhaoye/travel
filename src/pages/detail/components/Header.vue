<template>
<div>
  <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
    <div class="iconfont header-abs-icon">&#xe669;</div>
  </router-link>
  <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
    景点详情
    <router-link to="/">
      <div class="iconfont header-fixed-back">&#xe669;</div>
    </router-link>
  </div>
</div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data(){
    return{
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods:{
    handleScroll(){
      const top = document.documentElement.scrollTop;
      if(top > 60){
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      }else{
        this.showAbs = true
      }
      //console.log(document.documentElement.scrollTop)
    }
  },
  activated(){
    window.addEventListener('scroll', this.handleScroll)
  },deactivated(){
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
.header-abs
  position: absolute 
  left: .2rem
  top: .2rem
  width: .8rem
  height: .8rem
  border-radius: .4rem
  background: rgba(0, 0, 0, .7)
  .header-abs-icon
    color: #fff
    font-size: .4rem
    padding-left: .15rem
    padding-top: .15rem
.header-fixed
  position: fixed
  left: 0
  right: 0
  top: 0
  bottom: 0
  height: $headerHeight
  line-height: $headerHeight
  text-align: center
  color: #fff
  background: $bgColor
  font-size: .32rem
  z-index: 2
  .header-fixed-back
    position: absolute
    top: 0
    left: 0
    width: .64rem
    text-align: center
    font-size: .4rem
    color: #fff
</style>
