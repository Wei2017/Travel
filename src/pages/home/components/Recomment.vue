<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommentList" :key="item.id">
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
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecomment',
  data () {
    return {
      recommentList: [{
        id: '0001',
        imgUrl: 'https://img1.qunarzz.com/sight/p0/1511/d2/d2aec2dfc5aa771290.water.jpg_200x200_69e4a80d.jpg',
        title: '南山滑雪场',
        desc: '北京市密云县河南寨镇圣水头村',
        money: '120'
      },
      {
        id: '0002',
        imgUrl: 'https://img1.qunarzz.com/sight/p0/201303/04/50b65ba27d711f92c8d65eac.jpg_200x200_633f68b7.jpg',
        title: '小汤山温泉度假区',
        desc: '北京市昌平区小汤山现代农业科技示范园内',
        money: '75'
      },
      {
        id: '0003',
        imgUrl: 'https://img1.qunarzz.com/sight/p0/1411/43/dea8b51719a4a69b68777baa68c146e4.water.jpg_200x200_8da8cebe.jpg',
        title: '春晖园温泉度假村',
        desc: '北京市顺义区高丽营镇于庄',
        money: '112'
      },
      {
        id: '0004',
        imgUrl: 'https://img1.qunarzz.com/sight/p0/1602/67/67feeab24cfc82bb90.water.jpg_200x200_af2a01b1.jpg',
        title: '太平洋海底世界',
        desc: '北京市海淀区西三环中路11号中央电视塔下',
        money: '68'
      },
      {
        id: '0005',
        imgUrl: 'https://img1.qunarzz.com/sight/p0/1507/36/ce3d2d6c9ab44d67ae68d940b8781829.water.jpg_200x200_0938a8f2.jpg',
        title: '北京野生动物园',
        desc: '北京市大兴区一零六国道',
        money: '72'
      }]
    }
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
