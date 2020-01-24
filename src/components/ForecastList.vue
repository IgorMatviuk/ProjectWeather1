<template>
  <ul v-if="forecastWeather.length > 0" class="w-forecast-list">
    <ForecastListItem 
        v-for="(item, index) in forecastWeather" 
        :key="index" 
        :pos="index"
        :item="item" 
        :scale="scale" 
    >
    </ForecastListItem>
  </ul> 
</template>

<script>
import ForecastListItem from '@/components/ForecastListItem'
import { mapState } from 'vuex'

export default {
  name: 'ForecastList',
  components: {
    ForecastListItem
  },
  computed: {
    ...mapState([
      'forecastWeather',
      'scale'
    ])
  }
}

</script>
<style lang="css" scoped>
.w-forecast-list{
  display: flex;
  justify-content: center;
  margin: 100px;
  padding: 70px;
}
.w-forecast-list li{
  box-sizing: border-box;
  width: 20%
}
@media screen and (max-width: 1280px){

};
@media screen and (max-width: 1140px){

};
@media screen and (max-width: 992px){
.w-forecast-list{
  display: flex;
  justify-content: center;
  flex-direction: column;
  margin: 100px;
  padding: 70px;
}
.w-forecast-list li{
  box-sizing: border-box;
  width: 600px
}
};
@media screen and (max-width: 480px){

};
</style>