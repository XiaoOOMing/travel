<template>
  <div>
    <div class="banner">
      <img @click="handleBannerClick" src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg" class="banner-image">
      <div class="banner-info">
        <div class="image-number">
          <i class="iconfont">&#xe626;</i>
          10
        </div>
        <div class="title">故宫(AAAAA景区)</div>
      </div>
      <router-link class="back" to="/">
        <i class="iconfont">&#xe624;</i>
      </router-link>
    </div>
    <common-gallery @close="handleGalleryClose" v-show="showGallery" :images="images"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from '@/common/gallery/Gallery'

export default {
  name: 'Banner',
  data () {
    return {
      images: ['http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_r_800x800_6edd8174.jpg', 'http://img1.qunarzz.com/sight/p55/201211/04/fbcab3e5d6479ce893835fbb.jpg_r_800x800_6360f514.jpg'],
      showGallery: false
    }
  },
  components: {
    CommonGallery
  },
  methods: {
    handleBannerClick () {
      this.showGallery = true
    },
    handleGalleryClose () {
      this.showGallery = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    width 100%
    height 0
    padding-bottom 54.9%
    overflow hidden
    position relative
    .banner-image
      width 100%
    .banner-info
      position absolute
      width 100%
      bottom 0
      left 0
      font-size .36rem
      padding 0 .2rem
      color #fff
      .image-number
        background rgba(0,0,0,0.4)
        width 1.2rem
        text-align center
        border-radius .3rem
        font-size .24rem
        line-height .4rem
        display flex
        align-items center
        justify-content center
        .iconfont
          margin-right .02rem
      .title
        margin-top .11rem
        margin-bottom .38rem
    .back
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
</style>
