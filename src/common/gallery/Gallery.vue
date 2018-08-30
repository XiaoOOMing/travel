<template>
  <div class="container" @click="handleGalleryClick">
    <div class="wrapper">
      <swiper :options="swiperOption" v-show="images.length">
        <!-- slides -->
        <swiper-slide v-for="(item, key) of images" :key="key">
          <img :src="item" class="gallery-img">
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Gallery',
  props: {
    images: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleGalleryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container
    display flex
    flex-direction column
    justify-content center
    position fixed
    top 0
    left 0
    right 0
    bottom 0
    z-index 99
    background #000
    .wrapper
      width 100%
      height 0
      overflow hidden
      padding-bottom 100%
      .gallery-img
        width 100%
  .swiper-pagination
    position: fixed;
    bottom: .5rem;
    color: #fff;
</style>
