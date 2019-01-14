<template>
  <div>
    <div class="search">
      <input v-model="keyword" type="text" placeholder="输入成名或拼音" class="search-input">
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
      	<li class="search-item border-bottom" v-for="item in list">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: "CitySearch",
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((val) => {
            if(val.spell.indexOf(this.keyword) > -1 || val.name.indexOf(this.keyword) > -1){
              result.push(val)
            }
          })
        }
        this.list = result
      })
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    height:.72rem
    padding: 0 .1rem
    background:$bgColor
    .search-input
      width:100%
      height:.62rem
      line-height:.62rem
      padding:0 .1rem
      box-sizing:border-box
      text-align:center
      border-radius:.06rem
      color:#666
  .search-content
    overflow:hidden
    background:#eee
    z-index:1
    position:absolute
    top:1.58rem
    left:0
    right:0
    bottom:0
    .search-item
      line-height:.62rem
      padding-left:.2rem
      color:#666
      background:#fff
</style>
