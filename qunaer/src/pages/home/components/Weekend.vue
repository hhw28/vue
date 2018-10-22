<template>
  <div class="weekend">
    <div class="title">
      周末去哪儿
    </div>
    <ul>
      <li class="item" v-for="item of recommendList" :key="item.id">
        <div class="item-img">
          <img :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc" v-if="item.desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
        title: '杭州必游TOP10',
        desc: '杭州，前世今生与你有一场美丽约会'
      }, {
        id: '0002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/9f/7d45cc38259e0.jpg_r_640x214_156f4299.jpg',
        title: '承载杭城的历史之地',
        desc: '饱经沧桑的地方诉述着这座城的段段衷肠'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1509/8a/4cbf58944de788.jpg_r_640x214_1893da0a.jpg',
        title: '秋时景致美',
        desc: '火红的秋天，是杭州一年中最美的季节'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .weekend
    .title
      line-height .3rem
      height .3rem
      color $darkTextColor
      padding .26rem
    .item
      margin-bottom .1rem
      background #fff
      .item-img
        img
          width 100%
          height 37%
      .item-info
        padding  .14rem .2rem .2rem .2rem
        .item-title
          font-size .28rem
          line-height .48rem
          color $darkTextColor
          ellipsis()
          padding-right 1.4rem
        .item-desc
          font-size .24rem
          line-height .42rem
          color #616161
          ellipsis()
          padding-right 1.4rem
</style>
