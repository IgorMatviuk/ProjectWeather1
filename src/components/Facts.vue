<template>
  <div class="flex">
    <div class="cardtitle">
      <p>Интересные факты о погоде</p>
    </div>
     <div class="card">
       <p class="text">
         Районы мирового океана между 30° и 35° как северной, так и южной широты, иногда называют конскими широтами. Дело в том, что здесь преобладают антициклоны и часто бывают штили, которые вызывали задержки парусных судов. И во время особо длительных задержек из-за нехватки воды и пищи приходилось выбрасывать за борт лошадей.
       </p>
     </div>
    <div class="card">
       <p class="text">
         Самый первый телевизионный прогноз погоды был показан в Англии 11 ноября 1936 года. Сегодня же прогноз погоды можно узнать, не дожидаясь телевизионного эфира, всего навсего набрав прогноз погоды онлайн, например, погода в Москве на 3 дня на Oplao, никогда меня не обманывал и показывал самый точный прогноз из тех ,к которым я обращался ранее.
       </p>
     </div>
    <div class="card">
       <p class="text">
         В 1816 году на северо-востоке Соединенных Штатов морозы и снега наблюдались на протяжении всех 12 месяцев. Подобные метеоусловия преобладали также во Франции, Италии и Испании. В США и Европе назвали 1816 год "годом без лета".
       </p>
     </div>
  </div>
</template>

<script>
  export default {

  }
</script>

<style>
.flex{
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.card{
  display: flex;
  align-items: center;
  background: linear-gradient(45deg, #1414cf, #3742fa, #1e90ff, #70a1ff);
  box-shadow: 0 0 50px rgba(0,0,0,0.9);
  height: 350px;
  width: 900px;
  opacity: 0.8;
  color: white;
  margin: 10px 10px 100px 530px;

}
.cardtitle{
  display: flex;
  align-items: center;
  font-size: 40px;
  background: linear-gradient(45deg, #1414cf, #3742fa, #1e90ff, #70a1ff);
  box-shadow: 0 0 50px rgba(0,0,0,0.9);
  height: 100px;
  width: 600px;
  opacity: 0.8;
  color: white;
  margin: 10px 10px 100px 650px;
}
.text{
  font-size: 30px;
}

@media screen and (max-width: 1280px){
  .card{
  margin: 10px 10px 100px 230px;
}
.cardtitle{
  margin: 10px 10px 100px 380px;
}
};
@media screen and (max-width: 1140px){

};
@media screen and (max-width: 992px){

};
@media screen and (max-width: 480px){
  .card{
  margin: 10px 10px 100px 90px;
}
.cardtitle{
  margin: 10px 10px 100px 170px;
}
};

</style>