<template>
  <div>
  <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommand :list="recommendList"></home-recommand>
    <home-weeken :list="weekendList"></home-weeken>
  </div>
</template>

<script>
  import homeHeader from "./HomeHeader"
  import homeSwiper from "./HomeSwiper"
  import homeIcons from "./HomeIcons"
  import homeRecommand from "./HomeRecommand"
  import homeWeeken from './HomeWeeken'
  const axios = require('axios');

  export default {
        name: "home" ,
    data(){
         return{
           iconList:[],
           recommendList:[],
           swiperList:[],
           weekendList:[]
      }
    },
      components:{
          homeHeader,
          homeSwiper,
          homeIcons,
        homeRecommand ,
        homeWeeken
      } ,
    mounted(){
      axios.get('/static/mock/index.json')
        .then((response)=> {
          // handle success
          this.iconList = response.data.data.iconList
          this.recommendList = response.data.data.recommendList
          this.swiperList = response.data.data.swiperList
          this.weekendList = response.data.data.weekendList

        })
        .catch((error)=> {
          // handle error
          console.log("请求失败"+error);
        })
    }
    }
</script>

<style scoped lang="stylus">

</style>
