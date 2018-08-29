<template>
  <div class="start" :style="{width: maxWidth + 'rem'}">
    <i class="iconfont" v-for="(i,key) in 5" :key="key">&#xe8c2;</i>
  </div>
</template>

<script>
export default {
  name: 'Start',
  props: ['start'],
  computed: {
    maxWidth () {
      let start = this.start
      let s = this.start * 10 % 10
      if (s < 5) {
        start = Math.floor(start) + 0.5
      } else {
        start = Math.ceil(start)
      }
      return 1.2 * start / 5
    }
  }
}
</script>

<style lang="stylus" scoped>
  .start
    display flex
    justify-content flex-start
    overflow hidden
    width 1.2rem
    i
      font-size .24rem
      color #ffb436
      display block
      width .24rem
      height .24rem
</style>
