<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerimg">
      <div class="banner-info">
        <div class="banner-title">{{this.title}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe692;</span>
          {{this.imgs.length}}
        </div>
      </div>
    </div>
    <fade-animation>
      <common-gallary :imgs="imgs"
                      v-show="showGallary"
                      @close="handlecloseGallary">
      </common-gallary>
    </fade-animation>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  props: {
    title: String,
    bannerimg: String,
    imgs: Array
  },
  components: {
    CommonGallary,
    FadeAnimation
  },
  data () {
    return {
      showGallary: false
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
