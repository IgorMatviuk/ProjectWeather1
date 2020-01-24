<template>
  <div id="app">
    <Header></Header>
    <div class="flexsearch">
      <div class="fsearch">
      <div class="searchline">
        <div class="loading"  v-if="loading" >Loading... </div> 
        <Autocomplete 
          :items="items" 
          :value="init.city" 
          @item-selected="getData"
        ></Autocomplete>            
      </div>        
    </div>
    </div> 
    <div class="flexx">
  <div class="num">
            <WeatherInfo 
          :loading="loading" 
          @change-scale="setScale"
        ></WeatherInfo>
  </div>
  </div>
  <div>
    <ForecastList></ForecastList> 
  </div>
  <div>
    <Facts>
      <img src="" alt="">
    </Facts>
  </div>
  </div>
</template>

<script>
import Header from '@/components/Header'
import Facts from '@/components/Facts'
import Autocomplete from '@/components/Autocomplete'
import WeatherInfo from '@/components/WeatherInfo'
import ForecastList from '@/components/ForecastList'

import { initCity, cities } from '@/config'

export default {
  name: 'app',
  components:{
    Autocomplete,
    WeatherInfo,
    ForecastList,
    Facts,
    Header,
  },
  data () {
    return {
      init: initCity,
      items: cities,
      loading: true
    }
  },
  mounted: function(){
    this.getData(this.init);
  },
  methods: {
    async getData(valueSelected){
      this.loading = true
      await this.$store.dispatch('FETCH_WEATHER', valueSelected)
      this.loading = false
    },
    setScale(scale){
      this.$store.dispatch('SET_SCALE', scale)
    }
  }
}
</script>

<style>

.num{
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  background: linear-gradient(45deg, #1414cf, #3742fa, #1e90ff, #70a1ff);
  box-shadow: 0 0 50px rgba(0,0,0,0.9);
  height: 350px;
  width: 700px;
  opacity: 0.8;
  color: white;
}
.flexx{
  display: flex;
  justify-content: center;
}
.fsearch{
  width: 700px;
  height: 85px;
  opacity: 0.8;
  background: linear-gradient(45deg, #1414cf, #3742fa, #1e90ff, #70a1ff);
  box-shadow: 0 0 50px rgba(0,0,0,0.9);
}
.flexsearch{
  display: flex;
  justify-content:center; 
  margin-bottom: 50px;
  
}
.searchline{
  display: flex;
  align-items: center;
  
  width: 100%;
  height: 80px;
}
@media screen and (max-width: 1280px){

};
@media screen and (max-width: 1140px){

};
@media screen and (max-width: 992px){

.flexx{
  display: flex;
  justify-content: center;
  padding-left: 150px;
}
.flexsearch{
  display: flex;
  justify-content:center; 
  margin-bottom: 50px;
  padding-left: 150px;
}
};
@media screen and (max-width: 480px){

};


</style>

