<template>
<div>
  <div class="recommend-title">
  热销推荐
  </div>
  <ul>
    <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
      <img class="item-img" :src="item.imgUrl" />
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
        <button class="item-button">查看详情</button>
      </div>

    </li>
  </ul>


</div>
</template>

<script>

export default {
  name: 'HomeRecommend',
  data() {
    return {
        recommendList:[{
        id: '0001',
        imgUrl: "http://img1.qunarzz.com/sight/p18/201211/03/db9f2bb27ee40bf893835fbb.jpg_200x200_cf1de8d6.jpg",
        title: "美龄宫",
        desc: "位于南京市玄武区钟山风景名胜区"
      },{
        id: '0002',
        imgUrl: "http://img1.qunarzz.com/sight/p0/1511/ea/eaf1bdc38aed9e6690.img.jpg_200x200_3032bf56.jpg",
        title: "银杏湖乐园",
        desc: "位于南京市江宁区银杏湖大道520号"
      },{
        id: '0003',
        imgUrl: "http://img1.qunarzz.com/sight/p0/1411/bb/538133c76765880a3d3c802e45015c57.water.jpg_200x200_169b048c.jpg",
        title: "汤山紫清湖旅游区",
        desc: "位于南京市江宁区汤山镇"
      }]
    }
    
  }
  
  
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .recommend-title
    margin-top: .2rem
    line-height: .6rem
    background: #eee
    text-indent: .2rem
  .item
    display: flex
    height: 1.9rem
    // background: red
    .item-img
      width: 1.8rem
      height: 1.7rem
      padding .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        fontsize: .32rem
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top: .2rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
</style>
