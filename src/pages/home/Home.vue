<template>
  <div>
    <home-header></home-header>
  </div>
</template>

<script>
/* 引用组件 */
import HomeHeader from './components/HomeHeader'
export default{
  name: 'Home',
  /* 注册局部组件 */
  components: {
    HomeHeader
  }
}
</script>

<style>

</style>
