<script setup>
  import { ref } from 'vue';


  function al(){
    alert('ничего не произошло, попробуйте позже')
  }

  const imgs = ref([
    '/img/OIP.jpg',
    '/img/R.jpg',
    '/img/Заставки-в-хорошем-качестве-на-рабочий-стол-подборка-1.jpg'
  ])

  let currentSlide = ref(0);

  const next = () =>{
    if (currentSlide.value < imgs.value.length - 1) {
      currentSlide.value++;
    }
    else{
      currentSlide.value = 0;
    }
    
  }

  const prev = () =>{
    if (currentSlide.value > 0) {
      currentSlide.value--;
    }
    else{
      currentSlide.value = imgs.value.length - 1;
    }
    
  }
</script>

<template>
  <header>
  </header>
  <main>
    <div>
      <div class="action">
        <img src="/img/iphone.png" alt="">
        <div>
          <h3>Акция</h3>
          <p>Скидка 50%</p>
          <div></div>
          <span>до 23.04</span>
          <span>Цена $700.00 USD</span>
          <button @click="al">Register/ Login to buy/ BID</button>
          <span>ID акции: #0x2d0c8af807ef45ac17cafb2973d866ba8f38caa9</span>
          <span>Осталось в продаже 20,000</span>
        </div>
      </div>
      <div class="company">
        <h2>Компании которые пользуются нашими товарами</h2>
        <div>
          <div>
            <img src="/img/apple.png" alt="">
            <h5>Apple</h5>
            <span>ИНФА</span>
            <button><p>View details</p></button>
          </div>
          <div>
            <img src="/img/samsung.png" alt="">
            <h5>samsung</h5>
            <span>ИНФА</span>
            <button><p>View details</p></button>
          </div>
          <div>
            <img src="/img/xiaomi.png" alt="">
            <h5>xiaomi</h5>
            <span>ИНФА</span>
            <button><p>View details</p></button>
          </div>
          <div>
            <img src="/img/huawei.png" alt="">
            <h5>huawei</h5>
            <span>ИНФА</span>
            <button><p>View details</p></button>
          </div>
        </div>
      </div>
      <div class="wrapper">
        <div class="wraper">
          <img v-for="item in imgs" :key="item" :src="item" :style="{ transform: `translateX(${currentSlide * -100}%)` }">
        </div>
        <button @click="prev"><p>prev</p></button>
        <button @click="next"><p>next</p></button>
      </div>
    </div>
  </main>
</template>


<style scoped>
  header{
    background-image: url(/img/Rectangle.png);
    height: 100vh;
    background-repeat: no-repeat;
    background-size: cover;
  }
  main{
    background: #101029;
  }
  main > div{
    background-image: url(/img/background.png);
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding-bottom: 300px;
  }
  .action{
    margin-top: 100px;
    width: 60%;
    display: flex;
    align-items: center;
    background-color: rgba(30, 30, 55, 1);
    padding: 50px;
    justify-content: center;
    gap: 100px;
    box-sizing: border-box;
    color: white;
    border-radius: 50px;
  }
  .action > div{
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 100%;
    gap: 20px;
  }
  .action h3{
    font-size: 30px;
  }
  .action > div > div{
    width: 100%;
    border: 0.5px solid gray;
    border-radius: 1px;
  }
  .action button{
    width: 320px;
    border-radius: 46px;
    height: 50px;
    border: none;
    background: linear-gradient(270deg,#D70BCA, #5D00FA) ;
    color: white;
  }
  img{
    width: 460px;
    height: 460px;
  }







  .company{
    margin: 100px 0 100px 0;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .company h2{
    color: white;
    margin: 50px 0 50px 0;
    font-size: 30px;
  }
  .company > div{
    display: flex;
    gap: 100px;
  }
  .company > div > div{
    background: linear-gradient(200deg,#BB82DB 0%, #636DC1 19%, #1D0F35 100%);
    height: 450px;
    padding: 25px;
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    color: white;

  }
  .company > div > div h5{
    font-size: 25px;
  }
  .company img{
    width: 215px;
    height: 215px;
  }
  .company button{
    width: 180px;
    height: 50px;
    border-radius: 50px;
    border: none;
    transition: all .3s ease;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
  }
  .company button p{
    background: linear-gradient(270deg,#D70BCA, #5D00FA);
    -webkit-background-clip: text;
    color: transparent;
    display: inline-block;
    transition: all .3s ease;
  }

  .company button:hover{
    /* transform: scale(1.05); */
    box-shadow: 0 8px 18px rgba(0, 0, 0, 0.6);
  }

  .company button:focus {
    outline: none; 
  }

  .company button:active {
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);

  }

  .company button:hover{
    background: linear-gradient(270deg,#D70BCA, #5D00FA);
  }

  .company button:hover p{
    color: white;
  }






  div.wraper{
    display: flex;
    width: 500px;
    height: 300px;
    overflow: hidden;
  }

  .wraper img{
    width: 500px;
    height: 300px;
    transition: all .3s ease;
  }

  .wrapper button{
    width: 100px;
    height: 30px;
    border-radius: 50px;
    border: none;
    margin-top: 15px;
    transition: all .3s ease;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5);
  }

  .wrapper button:nth-child(2){
    margin-right: 300px;
  }

  .wrapper button p{
    background: linear-gradient(270deg,#D70BCA, #5D00FA);
    -webkit-background-clip: text;
    color: transparent;
    display: inline-block;
    transition: all .3s ease;
  }


  .wrapper button:hover{
    /* transform: scale(1.05); */
    box-shadow: 0 8px 18px rgba(0, 0, 0, 0.6);
  }

  .wrapper button:focus {
    outline: none;
  }

  .wrapper button:active {
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2); 

  }

  .wrapper button:hover{
    background: linear-gradient(270deg,#D70BCA, #5D00FA);
  }

  .wrapper button:hover p{
    color: white;
  }
</style>