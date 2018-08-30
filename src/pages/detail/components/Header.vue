<template>
  <div class="header">
    <router-link to="/" tag="div" class="header-abs" v-show="showAbs">
        <i class="iconfont">&#xe624;</i>
    </router-link>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <router-link to="/" tag="a" class="back">
        <i class="iconfont">&#xe624;</i>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>

export default {
  name: 'Header',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      let scrollTop = document.documentElement.scrollTop
      if (scrollTop > 60) {
        let opacity = scrollTop / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {opacity}
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import "~@style/var.styl"
  .header-abs
    position absolute
    left .1rem
    top .1rem
    width .72rem
    height .72rem
    line-height .72rem
    text-align center
    color #fff
    border-radius .36rem
    background #000
    opacity .5
    i
      font-size .32rem
      font-weight bold
  .header-fixed
    position fixed
    width 100%
    top 0
    height $topHeight
    line-height $topHeight
    background $bgClolor
    text-align center
    color #fff
    .back
      position absolute
      left 0
      top 0
      width $topHeight
      height $topHeight
      line-height $topHeight
      text-align center
      color #fff
      i
        font-weight bold
</style>
