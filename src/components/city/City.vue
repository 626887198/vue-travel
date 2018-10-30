<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :cities="cities" :hotCities="hotCities"></city-list>
  </div>
</template>

<script>
  import cityHeader from './CityHeader'
  import citySearch from './CitySearch'
  import cityList from './CityList'
  const axios = require('axios');
  export default {
    name: "city",
    components: {
      cityHeader,
      citySearch,
      cityList
    } ,
    data(){
      return{
         cities:{} ,
        hotCities:[]
      }
    },
    mounted(){
      axios.get('/static/mock/city.json')
        .then((response)=> {
          // handle success
         // console.log(response)
          this.cities = response.data.data.cities
          this.hotCities = response.data.data.hotCities

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
