<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
    <!-- slides -->
    <swiper-slide v-for="item in swiperList" :key="item.id">
      <img :src="item.url" class="swiper-img">
    </swiper-slide>
    <!-- Optional controls -->
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: 3000,
        loop: true
      },
      swiperList: [
        {
          id: '0001',
          url: 'http://img1.qunarzz.com/piao/fusion/1808/b0/a123fba6d7e3dd02.jpg_750x200_1425741a.jpg'
        },
        {
          id: '0002',
          url: 'http://img1.qunarzz.com/piao/fusion/1808/81/436f1adfbc86c402.jpg_750x200_64bb32af.jpg'
        },
        {
          id: '0003',
          url: 'http://img1.qunarzz.com/piao/fusion/1808/f4/5f2289f8675f0502.jpg_750x200_ab1633c7.jpg'
        },
        {
          id: '0004',
          url: 'http://img1.qunarzz.com/piao/fusion/1808/18/2dbce82b07a23402.jpg_750x200_14356b03.jpg'
        },
        {
          id: '0005',
          url: 'http://img1.qunarzz.com/piao/fusion/1801/bd/04554e7c67650302.jpg_750x200_4293d60a.jpg'
        },
        {
          id: '0006',
          url: 'http://img1.qunarzz.com/piao/fusion/1806/1c/4847ea66072c7b02.jpg_750x200_c32457fb.jpg'
        },
        {
          id: '0007',
          url: 'http://img1.qunarzz.com/piao/fusion/1807/40/1d7be74ed1584002.jpg_750x200_c41233c9.jpg'
        },
        {
          id: '0008',
          url: 'https://img1.qunarzz.com/piao/fusion/1808/df/7b0572d0e8dc002.png_750x200_9bdc6d1e.png'
        },
        {
          id: '0009',
          url: 'http://img1.qunarzz.com/piao/fusion/1804/bd/8e4a1c3f470d3702.jpg_750x200_f1f0a8c7.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper
    width 100%
    height 0
    overflow hidden
    padding-bottom 26.7%
    background-color #ddd
    .swiper-img
      width 100%
</style>
