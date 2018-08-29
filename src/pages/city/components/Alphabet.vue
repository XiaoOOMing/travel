<template>
  <ul class="alphabet">
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
    <li class="item">A</li>
  </ul>
</template>

<script>
export default {
  name: 'Alphabet'
}
</script>

<style lang="stylus" scoped>
  @import "~@style/var.styl"
  .alphabet
    position absolute
    display flex
    justify-content center
    flex-direction column
    top 1.58rem
    right 0
    bottom 0
    width .4rem
    .item
      color $bgClolor
      line-height .4rem
      text-align center
</style>
