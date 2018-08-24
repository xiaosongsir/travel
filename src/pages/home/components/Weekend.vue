<template>
  <div class="weekend-wrapper">
    <div class="title">周末去哪儿</div>
    <ul>
      <li
        class="item border-bottom"
        v-for="item of list"
        :key="item.id"
      >
        <div class="item-imggrid">
          <img class="item-img" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .weekend-wrapper
    background: #eee
    .title
      margin-top: .2rem
      line-height: .8rem
      background: #eee
      text-indent: .2rem
    .item
      margin-bottom: .1rem
      .item-imggrid
        overflow: hidden
        width: 100%
        height: 0
        padding-bottom: 37.08%
        .item-img
          width: 100%
      .item-info
        background: #fff
        padding: .1rem
        min-width: 0
        .item-title
          line-height: .54rem
          font-size: .28rem
          ellipsis()
        .item-desc
          line-height: .4rem
          font-size: .24rem
          color: #616161
          ellipsis()
</style>
