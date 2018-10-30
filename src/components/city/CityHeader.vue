<template>
 <div>
   <div class="out-wrapper">
     <i class="iconfont icon-houtui"></i>
     <div class="title">城市选择</div>
   </div>
 </div>
</template>

<script>
    export default {
        name: "city-header"
    }
</script>

<style scoped lang="stylus">
  @import "../../assets/stylus/variables.styl"
   .out-wrapper
      height $headerHeight
      width 100%
      background-color #525cff
      padding 10px
      display flex
      align-items center  //垂直居中
      .iconfont
         color white
         font-size 24px
      .title
         position absolute
         width 95%
         height $headerHeight
         display flex
         align-items center
         justify-content center    //内容居中对齐
         color white
</style>
