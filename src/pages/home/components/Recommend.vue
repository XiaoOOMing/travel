<template>
  <div class="home-recommend">
    <div class="recommend-title">
      <img class="mp-title-img" src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="猜你喜欢">
      <span class="title">猜你喜欢</span>
    </div>
    <ul class="like-list">
      <li v-for="item of recommend" :key="item.id" class="like-item border-bottom">
        <router-link to="/">
          <div class="like-img-wrapper">
            <img :src="item.imgUrl" class="like-img">
            <div class="mp-like-tag" style="background-image:url(https://img1.qunarzz.com/piao/fusion/1802/20/2ba6d10b17972e02.png)">随买随用</div>
          </div>
          <div class="like-info">
            <div class="like-title">{{ item.title }}</div>
            <div class="like-comments">
              <home-start :start="item.start"></home-start>
              <span class="comments">{{ item.comments }}条评论</span>
            </div>
            <div class="like-price">
              <span class="price">
                <span class="orange">￥{{ item.price }}</span>
                <span class="gray">起</span>
              </span>
              <span class="address">{{ item.address }}</span>
            </div>
          </div>
        </router-link>
      </li>
    </ul>
    <div class="recommend-title">
      <span class="title">周末去哪儿</span>
    </div>
    <ul class="like-list full-screen">
      <li v-for="item of weekend" :key="item.id" class="like-item border-bottom">
        <router-link to="/">
          <div class="like-img-wrapper">
            <img :src="item.imgUrl" class="like-img">
          </div>
          <div class="like-info">
            <div class="like-title">{{ item.title }}</div>
            <div class="like-desc">{{ item.desc }}</div>
          </div>
        </router-link>
      </li>
    </ul>
  </div>
</template>

<script>
import HomeStart from '@/pages/home/components/Start'

export default {
  name: 'HomeRecommend',
  props: {
    recommend: Array,
    weekend: Array
  },
  components: {
    HomeStart
  }
}
</script>

<style lang="stylus" scoped>
  .recommend-title
    padding .24rem 0
    line-height .44rem
    display flex
    background #f3f3f3
    .mp-title-img
      width .3rem
      height .3rem
      margin-left .2rem
    .title
      display: inline-block;
      margin-left: .08rem;
      height: .44rem;
      color: #212121;
      font-size: .32rem;
      line-height: .44rem;
  .like-list
    .like-item
      padding-left .2rem
      padding-right .2rem
      a
        display flex
        padding .2rem 0
        .like-img-wrapper
          width 2rem
          height 2rem
          position relative
          .mp-like-tag
            position absolute
            top 0
            left 0
            width 1.1rem
            height .45rem
            line-height .45rem
            font-size .24rem
            color #fff
            background-size 100%
            background-repeat no-repeat
            text-align center
          .like-img
            width 100%
            height 100%
        .like-info
          flex 1
          padding-left .2rem
          .like-title
            color #333
            margin-top .3rem
            font-size .32rem
          .like-comments
            display flex
            margin-top .3rem
            .comments
              font-size .24rem
              color #666
              margin-left .2rem
          .like-price
            margin-top .3rem
            display flex
            justify-content space-between
            align-items center
            .orange
              font-size .36rem
              color orange
            .gray,.address
              color #888
              font-size .24rem
    &.full-screen
      .like-item
        padding 0
      a
        display block
        .like-img-wrapper
          width 100%
          height auto
        .like-title
          color #333
          font-size .28rem !important
        .like-desc
          font-size .24rem
          color #666
          margin-top .2rem
</style>
