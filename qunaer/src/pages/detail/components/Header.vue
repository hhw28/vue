<template>
  <div class="header">
    <router-link tag="div" to="/" class="header-abs" v-show="showAbs">
      <span class="iconfont">&#xe624;</span>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      {{this.title}}
      <router-link tag="div" to="/" class="header-fixed-back">
        <span class="iconfont">&#xe624;</span>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  props: {
    title: String
  },
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
    // 当使用keep-alive组件的时候，会有activated钩子和deactivated钩子
    // 当使用当离开该页面的时候，会触发deactivated钩子，此时需清除全局事件避免该事件在其他页面也被触发
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    .header-abs
      position absolute
      left .2rem
      top .2rem
      width .72rem
      height .72rem
      border-radius .4rem
      text-align center
      color #fff
      line-height .72rem
      background rgba(0,0,0,.5)
    .header-fixed
      z-index 2
      background $bgColor
      color #fff
      width 100%
      height .86rem
      line-height .86rem
      font-size .32rem
      ellipsis()
      text-align center
      position fixed
      top 0
      left 0
      .header-fixed-back
        color #fff
        position absolute
        top 0
        left .16rem

</style>
