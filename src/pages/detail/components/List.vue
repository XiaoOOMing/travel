<template>
  <div class="list">
    <div>
      <div class="item border-bottom" v-for="(item, index) of list" :key="index">
        <div class="item-title">
          <span class="iconfont">&#xe659;</span>
          {{ item.title }}
        </div>
        <div v-if="item.children" class="item-children">
          <detail-list :list="item.children"></detail-list>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import "~@style/var.styl"
  .item-title
    line-height .8rem
    font-size .32rem
    padding 0 .2rem
    .iconfont
      color $bgClolor
  .item-children
    padding 0 .2rem
</style>
