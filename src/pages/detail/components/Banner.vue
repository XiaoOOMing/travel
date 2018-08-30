<template>
  <div>
    <div class="banner">
      <img @click="handleBannerClick" :src="bannerImg" class="banner-image">
      <div class="banner-info">
        <div class="image-number">
          <i class="iconfont">&#xe626;</i>
          {{ gallaryImgs.length }}
        </div>
        <div class="title">{{ sightName }}</div>
      </div>
    </div>
    <common-gallery @close="handleGalleryClose" v-show="showGallery" :images="gallaryImgs"></common-gallery>
  </div>
</template>

<script>
import CommonGallery from '@/common/gallery/Gallery'

export default {
  name: 'Banner',
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
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
</style>
