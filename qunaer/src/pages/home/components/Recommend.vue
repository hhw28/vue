<template>
  <div class="recommend">
    <div class="title">
      <img src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="">
      猜你喜欢
    </div>
    <ul>
      <router-link tag="li"
                   class="item"
                   v-for="item of list"
                   :key="item.id"
                   :to="'/detail/' + item.id"
      >
        <div class="item-img">
          <img :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-commend">{{item.commendNum}}条评论</p>
          <p class="item-price">
            <span class="item-price-num">￥<em>{{item.price}}</em></span>
            起
            <span class="address">{{item.address}}</span>
          </p>
          <p class="item-desc" v-if="item.desc">{{item.desc}}</p>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .recommend
    margin-top .2rem
    background #fff
    .title
      font-size .32rem
      line-height .44rem
      height .44rem
      color $darkTextColor
      padding .24rem 0 .26rem
      img
        width .3rem
        height .3rem
        margin-left .2rem
        vertical-align top
    .item
      border-bottom 1px solid #f1f1f1
      margin-left .2rem
      padding .2rem 0
      overflow hidden
      .item-img
        float left
        img
          width 2rem
          height 2rem
      .item-info
        padding-left .22rem
        overflow hidden
        .item-title
          margin-top .26rem
          font-size .32rem
          line-height .44rem
          height .44rem
          color $darkTextColor
        .item-commend
          color #616161
          font-size .24rem
          line-height .34rem
          vertical-align text-bottom
          margin-top .14rem
        .item-price
          margin-top .22rem
          font-size .24rem
          line-height .4rem
          color #616161
          position relative
          .item-price-num
            color #ff8300
            em
             font-size .4rem
          .address
            position absolute
            right .24rem
            bottom 0
        .item-desc
          display inline-block
          margin-top .48rem
          color #ff5555
          font-size .24rem
          line-height .34rem
          background #fff9f9
          padding .04rem .1rem

</style>
