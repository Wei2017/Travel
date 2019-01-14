<template>
  <div>
    <home-header :city="city"></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :icon="iconList"></home-icons>
    <home-recomment :list="recommentList"></home-recomment>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
/* 引用组件 */
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecomment from './components/Recomment'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default{
  name: 'Home',
  /* 注册局部组件 */
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecomment,
    HomeWeekend
  },
  data () {
    return {
      city: '',
      swiperList: [],
      iconList: [],
      /* 热销推荐 */
      recommentList: [],
      /* 周末去哪儿 */
      weekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      axios.get('/newTravel/static/mock/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.city = data.city
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommentList = data.recommendList
        this.weekendList = data.weekendList
        console.log(res)
      }
    }
  },
  /* 模板编译/挂载之后 生命周期钩子 */
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>

</style>
