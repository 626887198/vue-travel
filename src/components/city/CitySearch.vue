<template>
    <div>
      <div class="wrapper">
          <div class="input-wrapper iconfont icon-search">
            <input type="text" class="input-content" placeholder="输入城市或拼音"/>
          </div>
        </div>
      </div>

</template>

<script>
    export default {
        name: "city-search"
    }
</script>

<style scoped lang="stylus">
  @import "../../../src/assets/stylus/variables.styl"
  .wrapper
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


</style>
