<template>
    <div class="header">
      <div class="header-left">
        <i class="iconfont">&#xe624;</i>
      </div>
      <div class="header-center"><i class="iconfont">&#xe632;</i> 输入城市/景点/游玩主题</div>
      <router-link to="/city">
        <div class="header-right">{{ this.city }}<i class="iconfont">&#xe64a;</i></div>
      </router-link>
    </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  name: 'Header',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style lang="stylus" scoped>
  @import "~@style/var.styl"
  .header
    display flex
    align-items center
    height .88rem
    background-color $bgClolor
    color #fff
    .header-left
      width .4rem
      padding .2rem
      .iconfont
        font-size: .34rem;
        font-weight: bold;
        transform: translateX(-3px) translateY(-0.1px);
        display: block;
    .header-right
      width auto
      text-align center
      padding 0 .2rem
      color #fff
      line-height .88rem
      .iconfont
        font-size .26rem
        display: inline-block;
        transform: scaleY(.8);
    .header-center
      flex: 1
      line-height .58rem
      padding-left .20rem
      background-color #fff
      border-radius .08rem
      color #e4e7ea
</style>
