<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <router-link tag="li" class="item border-bottom" v-for="item of list" :key="item.id" :to="'/detail/' + item.id">
        <img :src="item.imgUrl" alt="" class="item-img">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-address">{{item.desc}}</p>
          <div class="item-money">
            <span class="m">&yen;</span>
            <span class="money">{{item.money}}</span>
            <span class="m m-r">起</span>
          </div>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecomment',
  props: {
    list: Array
  },
  data () {
    return {}
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    line-height: .8rem
    background: #eee
    text-indent: .2rem
  .item
    overflow:hidden
    display:flex
    height:1.9rem
    padding-bottom:.2rem
    .item-img
      width:1.7rem
      height:1.7rem
      padding:.2rem
    .item-info
      flex:1
      padding:.2rem
      min-width:0
      .item-title
        line-height:.54rem
        font-size:.32rem
        ellipsis()
      .item-address
        line-height:.4rem
        color:#ccc
        ellipsis()
      .item-money
        line-height:.44rem
        margin-top:.16rem
        border-radius:.06rem
        color:#ff8300
        font-size:0
        .money
          font-size:.4rem
        .m
          font-size:.24rem
        .m-r
          color:#333
</style>
