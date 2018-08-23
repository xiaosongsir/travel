<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [{
        id: '0001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1808/5e/514ce60160e62602.jpg_750x200_9b0074e2.jpg'
      }, {
        id: '0002',
        imgUrl: 'https://img1.qunarzz.com/piao/fusion/1808/df/7b0572d0e8dc002.png_750x200_9bdc6d1e.png'
      }, {
        id: '0003',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1808/16/074e0e717c92a602.jpg_750x200_37ec9a1b.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff !important
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 26.66%
    .swiper-img
      width: 100%
</style>
