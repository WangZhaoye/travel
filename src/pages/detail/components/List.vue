<template>
<div>
  <div 
    class="item"
    v-for="(item, index) of list"
    :key=index
  >
    <div class="item-title border-bottom">
      <span class="item-title-icon"></span>
      {{item.title}}
      <div v-if="item.children">
        <detail-list :list="item.children"></detail-list>

      </div>
    </div>
 </div>

</div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  .item-title
    line-height: .8rem
    font-size: .32rem
    padding: 0 .2rem
    .item-title-icon
      display: inline-block
      left: .06rem
      top: .07rem
      position: relative
      width: .36rem
      height: .36rem
      padding-right: .1rem
      background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
      background-size: .4rem 3rem
</style>
