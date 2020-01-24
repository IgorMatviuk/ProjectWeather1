<template>
    <header>
    <div class="logo">
      <div>
      <p class="logo__1">Project</p>
    </div>
    <div>
      <p class="logo__2">Zeus</p> 
    </div>
    </div>
    <div class="titletext">
      <p>Lightning weather</p>
    </div>
    </header>
</template>
<script>
export default {
  
}
</script>
<style scoped>
header{
    display: flex;
    height: 200px;
    width: 1000px;
    margin: 50px 10px 50px 500px;
    background: linear-gradient(45deg, #1414cf, #3742fa, #1e90ff, #70a1ff);
    box-shadow: 0 0 50px rgba(0,0,0,0.9);
    align-items: center;
    justify-content: center;
    opacity: 0.8;
    flex-direction: column;
}
.titletext{
    font-size: 40px;
    letter-spacing: 15px;
    color: white;
}
.logo{
    font-size: 80px;
    display: flex;
    border-radius: 5%;
}
.logo__1{
    color: white;
}
.logo__2{
    background: linear-gradient(45deg, #1414cf, #4d55f1);
    color: white;
    border-radius: 5%;
    padding: 10px;
    font-family: 'Anton', sans-serif;
    letter-spacing: 5px;
    margin-left: 5px;
}
@media screen and (max-width: 1280px){
header{
    display: flex;
    height: 200px;
    width: 900px;
    margin: 50px 10px 50px 200px;
   
}
};
@media screen and (max-width: 1140px){
header{
    display: flex;
    height: 200px;
    width: 900px;
    margin: 50px 10px 50px 130px;
}   
};
@media screen and (max-width: 992px){

};
@media screen and (max-width: 480px){
header{
    display: flex;
    height: 200px;
    width: 700px;
    margin: 50px 10px 50px 130px;
}       
};

</style>