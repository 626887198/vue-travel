<template>
  <div class="out-wrapper">
    <div class="section">
      热销推荐
    </div>
    <div class="item-wrapper" v-for="item,index in list" :key="index">
      <img
        :src="item.imgUrl"
        alt="" class="item-img">
      <div class="item-content">
        <div class="content-title">{{item.title}}</div>
        <div class="content-desc">{{item.desc}}</div>
        <div class="content-detail">查看详情</div>
      </div>
    </div></div>
</template>

<script>

  export default {
    name: "home-recommand",
    props:['list'],
    data() {
      return {
      }
    }
  }
</script>

<style scoped lang="stylus">
  .out-wrapper
    .section
      background-color #eee
      margin-top 8px
      padding 12px
      font-size 18px
    .item-wrapper
      display flex
      padding 10px
      border-bottom solid 1px #eee
      .item-img
        width 100px
        height 100px
      .item-content
        margin-left 10px
        display: flex
        flex-direction column
        justify-content space-around
        .content-desc
          color #999
          font-size 18px
        .content-detail
          width fit-content
          background-color #ff9300
          border solid 1px #ff9300
          border-radius 4px
          font-size 18px
          padding 2px
          color #fff
</style>
