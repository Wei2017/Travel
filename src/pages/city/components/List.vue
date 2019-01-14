<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrap">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrap">
            <div class="button">北京</div>
          </div>
          <div class="button-wrap">
            <div class="button">上海</div>
          </div>
          <div class="button-wrap">
            <div class="button">广州</div>
          </div>
          <div class="button-wrap">
            <div class="button">深圳</div>
          </div>
          <div class="button-wrap">
            <div class="button">成都</div>
          </div>
          <div class="button-wrap">
            <div class="button">郑州</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
        </div>
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
        </div>
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
        </div>
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
        </div>
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿拉尔</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: "CityList",
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:after
      border-color:#ccc
    &:before
      border-color:#ccc
  .border-bottom
    &:before
      border-color:#ccc
  .list
    overflow:hidden
    position:absolute
    top:1.58rem
    left:0
    right:0
    bottom:0
    .title
      line-height:.54rem
      background:#eee
      padding-left:.2rem
      font-size:.26rem
      color:#666
    .button-list
      overflow:hidden
      padding:.1rem .6rem .1rem .1rem
      .button-wrap
        width:33.33%
        float:left
        .button
          text-align:center
          padding:.1rem 0
          border-radius:.06rem
          margin:.1rem
          border:.02rem solid #ccc
    .item-list
      .item
        line-height:.76rem
        color:#666
        padding-left:.2rem
</style>
