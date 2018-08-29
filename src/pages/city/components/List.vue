<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
          <div class="button-wrapper">
            <div class="button">北京</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">A</div>
        <div class="item-list">
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
          <div class="item border-bottom">阿拉尔</div>
          <div class="item border-bottom">阿坝</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'

export default {
  name: 'List',
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  .list
    position absolute
    overflow hidden
    top 1.58rem
    left 0
    right 0
    bottom 0
  .title
    line-height .54rem
    font-size .26rem
    color #666
    background #eee
    padding-left .2rem
  .button-list
    overflow hidden
    align-items center
    padding .1rem
    padding-top .2rem
    .button-wrapper
      float left
      width calc(100% / 3 - .1rem)
      margin-left .1rem
      margin-bottom .1rem
      .button
        border-radius .06rem
        padding .1rem 0
        border 1px solid #ddd
        text-align center
  .item-list
    .item
      line-height .76rem
      color #666
      padding-left .2rem
      &:before
        border-color #999
</style>
