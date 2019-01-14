<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index" >
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="img-content" :src="item.imgUrl"  />
          </div>
          <p class="keywords">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    icon: Array
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.icon.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    padding: 0.2rem 0;
  .icon
    float: left
    width: 25%
    height: 1.5rem
    padding-top: .1rem
    text-align: center
    .icon-img
      width: 1.1rem
      height: 1.1rem
      display:inline-block
      .img-content
        width: 1.1rem
        height: 1.1rem
        background: 0
    .keywords
      margin-top: .1rem
      color: $darkTextColor
      ellipsis()
</style>
