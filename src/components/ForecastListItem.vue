<template>
	<li>
      <div class="fc-date">{{ item.datetime | dayWeek(pos) }}</div>
      <div class="fc-icon"><img :src='icon' :alt='item.weather.condition' :title='item.weather.condition'></div>
      <div class="fc-maxmin" ><span><strong>{{ item.max_temp | tempScale(scale) }}&deg;</strong></span> <span>{{ item.min_temp | tempScale(scale) }}&deg;</span></div>
	</li>
</template>

<script>
import dayjs from 'dayjs'
import { baseImg } from '@/config'
import { weatherMixins } from '@/mixins/weatherMixins'

export default {
  name: 'ForecastListItem',
  mixins: [weatherMixins],  
  props: ['pos', 'item', 'scale'],
  data () {
    return {
      baseImg
    }
  },  
  computed: {
    icon(){
      return `${this.baseImg}${this.item.weather.icon}.png`
    }
  },
  filters:{
    dayWeek(value, pos)  {
        return (pos == 0) ? 'TODAY' : dayjs(value).format('ddd').toUpperCase();
    }
  }  

}
</script>

<style >
li{
  
  color: white;
  border-right: 1px dotted #505d64;
  text-align: center;
  font-size: 15px;
  display: flex;
  -webkit-flex-flow: column wrap;
  flex-flow: column wrap;
  flex-grow: 1;
  justify-content: center;
  background: linear-gradient(45deg, #1414cf, #3742fa, #1e90ff, #70a1ff);
  box-shadow: 0 0 50px rgba(0,0,0,0.9);
  height: 350px;
  opacity: 0.8;
  margin: 10px 10px 10px 10px;
}

li:last-child{
  border: none;
}

.fc-icon img{
  width: 50px;
  height: 50px;
}
.fc-maxmin span{
  padding: 3px;
    color: white;
  font-family: 'Rubik', sans-serif;
  font-size: 40px;
}
.fc-maxmin  strong{
  color: white;
  font-family: 'Rubik', sans-serif;
  font-size: 40px;
}
@media screen and (max-width: 1280px){
.fc-maxmin span{
  padding: 3px;
    color: white;
  font-family: 'Rubik', sans-serif;
  font-size: 20px;
}
};
@media screen and (max-width: 1140px){

};
@media screen and (max-width: 992px){

  
};
@media screen and (max-width: 480px){

};


</style>