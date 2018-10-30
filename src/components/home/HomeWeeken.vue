<template>
  <div class="wrapper">
    <div class="section">周末去哪儿</div>

    <div class="item-wrapper" v-for="item,index in list" :key="index">
      <img
        class='img-wrapper'
        :src="item.imgUrl"
        alt="">
      <div class="item-title">{{item.title}}</div>
      <div class="item-content">{{item.desc}}</div>
    </div>

  </div>
</template>

<script>
  export default {
    name: "HomeWeekend",
    props:['list'],
    data(){
      return{
      }
    }
  }
</script>

<style scoped lang='stylus'>
  .wrapper
    .section
      background-color #eee
      margin-top 8px
      padding 12px
      font-size 18px
    .item-wrapper
      .img-wrapper
        width 100%
      .item-title
        padding-left 10px
        font-size 20px
        line-height 36px
      .item-content
        color #999
        padding-left 10px
        padding-bottom 10px
</style>

