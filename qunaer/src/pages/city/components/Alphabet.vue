<template>
    <ul class="list">
      <li v-for="(item, key) of cities" :key="key">{{key}}</li>
    </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
}
</script>

<style lang="stylus" scoped>
  .list
    position fixed
    top 25%
    right 0
</style>
