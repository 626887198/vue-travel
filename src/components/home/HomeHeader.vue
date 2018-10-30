<template>
    <div class="wrapper">
      <div class="header-wrapper">
       <i class="back iconfont icon-houtui"></i>
        <div class="input-wrapper iconfont icon-search">
         <input type="text" class="input-content" placeholder="输入城市/景点/主题"/>
        </div>
        <div class="city-wrapper" @click="handClick">
          深圳
          <i class="xiala iconfont icon-xiala1"></i>
        </div>
      </div>
    </div>
</template>

<script>
    export default {
        name: "home-header",
      methods:{
        handClick(){
          this.$router.push('/city')
        }
      }

    }
</script>

<style scoped lang="stylus">
  @import "../../../src/assets/stylus/variables.styl"
  .wrapper
    .header-wrapper
      display flex
      align-items center
      height $headerHeight
      background #525cff
      .back
        color white
        font-size 24px
      .input-wrapper
        display flex
        height 35px
        flex 1
        background-color white
        color #ccc
        border solid 1px #fff
        border-radius 4px
        margin-left 10px
        margin-right 10px
        align-items center
       .input-content
          flex 1
          border 0
          height 25px
      .city-wrapper
         color white
         vert-align  center
        .xiala
          color white

</style>
