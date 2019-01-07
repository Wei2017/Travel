<template>
  <div>
    <home-header></home-header>
    <home-swiper></home-swiper>
  </div>
</template>

<script>
/* 引用组件 */
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
export default{
  name: 'Home',
  /* 注册局部组件 */
  components: {
    HomeHeader,
    HomeSwiper
  }
}
</script>

<style>

</style>
