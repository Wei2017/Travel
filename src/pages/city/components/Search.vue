<template>
  <div class="search">
    <input type="text" placeholder="输入成名或拼音" class="search-input">
  </div>
</template>

<script>
export default {
  name: "CitySearch"
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
</style>
