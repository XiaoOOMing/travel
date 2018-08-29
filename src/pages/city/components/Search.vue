<template>
  <div>
    <div class="city-search">
      <input v-model="kw" type="text" placeholder="输入城市名或拼音" class="search-input" />
    </div>
    <div class="search-content" ref="search" v-show="kw">
      <ul>
          <li class="search-item border-bottom" v-for="(item,key) of list" :key="key">{{ item }}</li>
        <li class="search-item border-bottom" v-show="hasNoData">没有找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'

export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      kw: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    kw () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.kw) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const res = []
        for (let i in this.cities) {
          this.cities[i].forEach((val) => {
            if (val.spell.includes(this.kw) || val.name.includes(this.kw)) {
              res.push(val.name)
            }
          })
        }
        this.list = res
      }, 100)
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  }
}
</script>

<style lang="stylus" scoped>
  @import "~@style/var.styl"
  .city-search
    background $bgClolor
    height .72rem
    padding 0 .1rem
    .search-input
      box-sizing border-box
      width 100%
      padding 0 .1rem
      height .62rem
      line-height .62rem
      text-align center
      border-radius .06rem
      color #666
  .search-content
    top 1.58rem
    left 0
    right: 0
    bottom: 0
    position: absolute
    z-index 9
    background #eee
    overflow hidden
    .search-item
      color #666
      background #fff
      line-height .62rem
      padding-left .2rem
</style>
