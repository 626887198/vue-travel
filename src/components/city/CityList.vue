<template>
  <div>
  <div  class="wrapper" ref="wrapper">
    <div class="out-wrapper">
      <div class="section">
        当前城市
      </div>
      <div class="cur-city">深圳</div>

      <div class="section">
        热门城市
      </div>
      <div class="hot-wrapper">
      <div class="hot-city" v-for="item,index in hotCities" :key="index">{{item.name}}</div>
      </div>
      <div class="item-wrapper"  v-for="item,key,index in cities" :key="index" :ref="key">
        <div class="section">
          {{key}}
        </div>
        <div class="item-title" v-for="city,index in item" :key="index">{{city.name}}</div>
      </div>
    </div>
  </div>
    <!--右侧字母-->
    <div class="letter-wrapper" >
    <div class="letter" v-for="item,index in letters" @click="()=>handLetterClick(item)">{{item}}</div>
    </div>
  </div>
</template>

<script>
  import BScroll from 'better-scroll'
  export default {
    name: "city-list" ,
    props:['cities','hotCities'] ,
    mounted(){
      const ele = this.$refs.wrapper
      // console.log(ele)
      this.scroll = new BScroll(ele)
    },
    computed:{
      letters(){
           let arr=[]
        for (let key in this.cities) {
            arr.push(key)
        }
        return arr
      }
    },
    methods:{
      handLetterClick(letter){
         // console.log(item)
        this.scroll.scrollToElement(this.$refs[letter][0])
      }
    }
  }
</script>

<style scoped lang="stylus">

   .wrapper
     position absolute
     top 110px
     bottom 0px
     left 0px
     right 0px
     z-index 1
     overflow hidden
     .out-wrapper
      .section
        background-color #eee
        padding 12px
        font-size 18px
      .cur-city
        margin-top 15px
        margin-bottom 15px
        margin-left 20px
        padding 8px
        border solid 1px #ccc
        width 25%
        text-align center
        border-radius 5px
      .hot-wrapper
        display flex
        flex-wrap: wrap
        padding-bottom  15px
        .hot-city
          margin-top 20px
          margin-bottom 1px
          margin-left 20px
          padding 8px
          border solid 1px #ccc
          width 25%
          text-align center
          border-radius 5px
      .item-wrapper
        padding-top  0px
        .item-title
           color #666
           padding 10px
           border-bottom solid 1px #eee
   .letter-wrapper
     position absolute
     z-index 2
     right 0
     top 110px
     bottom 0
     .letter
       font-size 14px
       height 20px
       padding 6px
       padding-top 10px
       text-align center
</style>
