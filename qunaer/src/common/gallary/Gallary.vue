<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item, index) of imgs" :key="index">
          <img class="swiper-img" :src="item">
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction', // 页码显示数字
        // 当Swiper父元素发生变化，更新Swiper
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow inherit
  .container
    z-index 1
    display flex
    flex-direction column
    justify-content center
    position fixed
    top 0
    left 0
    right 0
    bottom 0
    background #000
    .wrapper
      width 100%
      height 0
      padding-bottom 60%
      .swiper-img
        width 100%
      .swiper-pagination
        color #fff
        bottom -1rem
</style>
