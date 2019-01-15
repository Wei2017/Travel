<template>
  <div>
    <detail-banner></detail-banner>
  </div>
</template>

<script>
/* 引用组件 */
import DetailBanner from './components/Banner'


export default{
  name: 'Detail',
  /* 注册局部组件 */
  components: {
    DetailBanner
  }
}
</script>

<style lang="stylus" scoped>

</style>
