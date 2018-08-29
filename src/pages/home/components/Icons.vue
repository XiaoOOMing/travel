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
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      }
    }
  },
  computed: {
    icons () {
      let icons = []
      let iconNumber = 8
      this.list.forEach(function (item, index) {
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
  .home-icons >>> .swiper-pagination-bullets
    bottom 12px
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
