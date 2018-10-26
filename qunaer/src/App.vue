<template>
  <div id="app">
    <!--
      使用keep-alive会缓存ajax请求，当进入同一个页面时不会一直发送请求
      exclude属性定义不受keep-alive限定，如下进去Detail页面时还是会发送请求
     -->
    <keep-alive exclude="Detail">
      <router-view/>
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>

</style>
