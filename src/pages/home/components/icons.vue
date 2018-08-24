<template>
  <div class="icons-wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <a class="icon-grid" v-for="item of page" :key="item.id" href="">
          <div class="icon">
            <img :src="item.imgUrl" alt="" class="icon-img">
          </div>
          <p class="desc">{{item.desc}}</p>
        </a>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcon',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        loop: true
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    },
    showSwiper () {
      return this.list.length
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons-wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 50%
    .icon-grid
      display: block
      float: left
      position: relative
      overflow: hidden
      width: 25%
      height: 0
      padding-bottom: 25%
      .icon
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: 0.4rem
        box-sizing: border-box
        padding: 0.2rem
        text-align: center
        .icon-img
          height: 100%
      .desc
        position: absolute
        left: 0
        right: 0
        bottom: 0
        height: 0.4rem
        line-height: 0.4rem
        text-align: center
        color: $darkTextColor
        ellipsis()
</style>
