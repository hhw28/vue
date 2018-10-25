<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1810/14/14b8a787d6e901f6a3.img.jpg_600x330_7ee67553.jpg">
      <div class="banner-info">
        <div class="banner-title">杭州云曼温泉</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe692;</span>
          15
        </div>
      </div>
    </div>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handlecloseGallary"></common-gallary>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary
  },
  data () {
    return {
      showGallary: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1810/14/14b8a787d6e901f6a3.img.jpg_r_800x800_3395de40.jpg', 'http://img1.qunarzz.com/sight/p0/1810/14/14b8a787d6e901f6a3.img.jpg_r_800x800_3395de40.jpg']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handlecloseGallary () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    overflow hidden
    height 0
    padding-bottom 55%
    .banner-img
      width 100%
    .banner-info
      display flex
      position absolute
      left 0
      right 0
      bottom 0
      line-height .6rem
      color #fff
      background-image linear-gradient(top ,rgba(0,0,0,0), rgba(0,0,0,.6))
      .banner-title
        flex 1
        font-size .36rem
        padding .1rem .2rem
        text-shadow 0 1px 2px rgba(0,0,0,.7)
      .banner-number
        padding 0 .4rem
        margin-top .22rem
        margin-right .2rem
        line-height .32rem
        height .32rem
        border-radius .2rem
        background  rgba(0, 0, 0, .5)
        font-size .24rem
        .banner-icon
          font-size .24rem

</style>
