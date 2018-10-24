<template>
  <div class="list">
    <div class="area">
      <div class="title">当前城市</div>
      <div class="button-list">
        <div class="button-wrapper">
          <div class="button">北京</div>
        </div>
      </div>
    </div>
    <div class="area">
      <div class="title">热门城市</div>
      <div class="button-list">
        <div class="button-wrapper" v-for="city of hot" :key="city.id">
          <div class="button">{{city.name}}</div>
        </div>
      </div>
    </div>
    <div class="area" v-for="(item, key) of cities" :key="key">
      <div class="title">{{key}}</div>
      <div class="button-list">
        <div class="button-wrapper" v-for="city of item" :key="city.id">
          <div class="button">{{city.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hot: Array
  }
}
</script>

<style lang="stylus" scoped>

</style>
