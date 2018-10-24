<template>
  <div class="header">
    <div class="header-left">
      <span class="iconfont">&#xe624;</span>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点、游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right ">
        {{this.city}}
        <span class="iconfont">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default{
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    line-height: .86rem
    background: $bgColor
    display: flex
    color: #fff
    .header-left
      width: .64rem
      text-align: center
    .header-input
      flex: 1
      line-height: .64rem
      margin-top: .12rem
      margin-bottom: .12rem
      padding-left: .2rem
      border-radius: .1rem
      background: #fff
      color: #ccc
      .iconfont
        vertical-align: middle
    .header-right
      width: 1.24rem
      float: right
      text-align: center
      color #fff

</style>
