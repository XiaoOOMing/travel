<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="header-back">
        <i class="iconfont">&#xe624;</i>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import "~@style/var.styl"
  .header
    height .86rem
    line-height .86rem
    overflow hidden
    text-align center
    color #fff
    background $bgClolor
    position relative
    .header-back
      position absolute
      left 0
      top 0
      color #fff
      font-weight bold
      font-size .34rem
      width .86rem
      height .86rem
      line-height .86rem
      text-align center
</style>
