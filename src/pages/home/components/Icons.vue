<template>
  <div class="home-icons">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="(icon,key) of icons" :key="key">
        <div class="icon" v-for="item of icon" :key="item.id">
          <div class="center">
            <img :src="item.icon" class="icon-img">
            <p>{{ item.name }}</p>
          </div>
        </div>
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      },
      iconList: [
        {
          id: '0001',
          icon: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          name: '景点门票'
        },
        {
          id: '0002',
          icon: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          name: '北京必游'
        },
        {
          id: '0003',
          icon: 'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
          name: '夏日玩水'
        },
        {
          id: '0004',
          icon: 'http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png',
          name: '文化古迹'
        },
        {
          id: '0005',
          icon: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
          name: '动植物园'
        },
        {
          id: '0006',
          icon: 'http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png',
          name: '故宫'
        },
        {
          id: '0007',
          icon: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          name: '一日游'
        },
        {
          id: '0008',
          icon: 'http://img1.qunarzz.com/piao/fusion/1804/95/8d02011d149bdb02.png',
          name: '汽车票'
        },
        {
          id: '0009',
          icon: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png',
          name: '游乐场'
        },
        {
          id: '0010',
          icon: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
          name: '全部玩乐'
        }
      ]
    }
  },
  computed: {
    icons () {
      let icons = []
      let iconNumber = 8
      this.iconList.forEach(function (item, index) {
        let page = Math.floor(index / iconNumber)
        if (!icons[page]) {
          icons[page] = []
        }
        icons[page].push(item)
      })
      return icons
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import "~@style/var.styl"
  @import "~@style/mixins.styl"
  .home-icons >>> .swiper-container
    padding-bottom: .6rem;
  .home-icons >>> .swiper-pagination-bullet
    background rgba(144,144,144,0.8)
  .home-icons >>> .swiper-pagination-bullet-active
    background rgba(0,175,190,.8)
  .home-icons
    width 100%
    height 0
    padding-bottom 50.67%
    overflow hidden
    .icon
      width 25%
      height 0
      padding-bottom 22%
      float left
      position relative
      .center
        width 100%
        position absolute
        top 59%
        transform translateY(-50%)
      .icon-img
        width: 58%;
        display: block;
        margin: 0 auto;
      p
        line-height .48rem
        text-align center
        color $darkTextColor
        ellipses()
</style>
