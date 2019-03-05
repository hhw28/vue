<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    background $bgColor
    color #fff
    height .86rem
    line-height .86rem
    font-size .32rem
    ellipsis()
    text-align center
    position relative
    .header-back
      color #ff
      position absolute
      top 0
      left .16rem
</style>
