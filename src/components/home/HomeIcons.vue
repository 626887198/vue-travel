<template>
  <div class="wrapper">

    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="page,index in pages" :key="index">
        <div class="page-wrapper">
          <div class="item-wrapper" v-for="item,index in page" :key="index">
            <img :src="item.imgUrl" alt="" class="img-wrapper">
            <div>{{item.desc}}</div>
          </div>
        </div>
        <!-- Optional controls -->
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper-slide>

    </swiper>

  </div>
</template>

<script>
  import 'swiper/dist/css/swiper.css';
  import {swiper, swiperSlide} from 'vue-awesome-swiper'

  export default {
    name: "home-icons",
    props:['list'],
    components: {
      swiper,
      swiperSlide
    },
    data() {
      return {
        swiperOption: {
          // pagination: '.swiper-pagination',
          loop: false,
          autoplay: 0,
          autoplayDisableOnInteraction: false
        },

      }
    },
    computed: {
      pages() {
        //每页8个
        let pageLimit = 8
        //数组长度
        let length = this.list.length
        //页数
        let page = (length + pageLimit - 1) / pageLimit
        page = parseInt(page)
        //存放每一页的数据
        let arr = []
        for (let i = 0; i < page; i++) {
          arr.push(this.list.slice(i * pageLimit, (i + 1) * pageLimit))
        }
        // console.log(arr)
        return arr
      }
    }

  }
</script>

<style scoped lang="stylus">
  .wrapper
    display: flex;
    flex-wrap: wrap;
    .page-wrapper
      display: flex;
      flex-wrap: wrap;
      .item-wrapper
        width 25%
        text-align center
        .img-wrapper
          width 70px
          hight 70px
          margin-top 5px
</style>
