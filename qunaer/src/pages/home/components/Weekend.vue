<template>
  <div class="weekend">
    <div class="title">
      周末去哪儿
    </div>
    <ul>
      <li class="item" v-for="item of list" :key="item.id">
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
  props: {
    list: Array
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
