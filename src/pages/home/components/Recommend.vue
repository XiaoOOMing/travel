<template>
  <div class="home-recommend">
    <div class="recommend-title">
      <img class="mp-title-img" src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="猜你喜欢">
      <span class="title">猜你喜欢</span>
    </div>
    <ul class="like-list">
      <li v-for="item of recommendList" :key="item.id" class="like-item border-bottom">
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
      <li v-for="item of weekendList" :key="item.id" class="like-item border-bottom">
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
  data () {
    return {
      recommendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1609/7a/7ae8ee7831836095a3.water.jpg_200x200_36727f69.jpg',
          title: '金海湖风景区',
          comments: 1440,
          start: 4.1,
          price: 24,
          address: '平谷区'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg',
          title: '故宫',
          comments: 273332,
          start: 5,
          price: 20,
          address: '东城区'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1508/a5/4003f9dd7bebf61eccbf64046e26d487.water.jpg_200x200_7690e4cd.jpg',
          title: '北京欢乐谷',
          comments: 57608,
          start: 5,
          price: 29.9,
          address: '朝阳区'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/36/ce3d2d6c9ab44d67ae68d940b8781829.water.jpg_200x200_0938a8f2.jpg',
          title: '北京野生动物园',
          comments: 12788,
          start: 3.4,
          price: 71,
          address: '大兴区'
        }
      ],
      weekendList: [
        {
          id: '0001',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1606/85/c6b6bad1b977e.jpg_r_640x214_5c638941.jpg',
          title: '漂流勇进，烧烤露营',
          desc: '轻松水上漂，任我乐逍遥'
        },
        {
          id: '0002',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/53/02091f1ee43d0a.jpg_r_640x214_2e3256b1.jpg',
          title: '北京清凉避暑胜地',
          desc: '到大自然中享受“天然空调”的清凉'
        },
        {
          id: '0003',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
          title: '北京必游TOP10',
          desc: '来北京必去的景点非这些地方莫属'
        },
        {
          id: '0004',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
          title: '寻找北京的皇城范儿',
          desc: '数百年的宫廷庙宇，至今依旧威严霸气'
        },
        {
          id: '0005',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/ce/bc89bc2f0e33ea.jpg_r_640x214_3e408453.jpg',
          title: '学生最爱的博物馆',
          desc: '周末干嘛？北京很多博物馆已经免费开放啦'
        }
      ]
    }
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
