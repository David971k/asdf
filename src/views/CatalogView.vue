<script setup>
  import { ref } from 'vue';
  import card from '@/components/Card.vue';
  import { useCounterStore } from '../stores/counter.js';

  const counter = useCounterStore();

  let id = 1;



  const tovarList = ref([
    {id: id++, name: 'iPhone 16 Pro Max',  src: '/img/iphone16promax.png',   price: 3000,  inCorzina: false, butText: "В корзину"  },
    {id: id++, name: 'Samsung Galaxy S24', src: '/img/samsungGalaxyS24.png', price: 500,  inCorzina: false, butText: "В корзину"  },
    {id: id++, name: 'HUAWEI Pura 70 Pro', src: '/img/HuaweiPura70Pro.png',  price: 400,  inCorzina: false, butText: "В корзину"  },
    {id: id++, name: 'iPhone 16 Pro',      src: '/img/iphone16.png',         price: 2000,  inCorzina: false, butText: "В корзину"  },
    {id: id++, name: 'Xiaomi Redmi 12',    src: '/img/XiaomiRedmi12.png',    price: 550,  inCorzina: false, butText: "В корзину"  },
    {id: id++, name: 'Xiaomi 13T Pro',     src: '/img/Xiaomi13TPro.png',     price: 600,  inCorzina: false, butText: "В корзину"  },
    {id: id++, name: 'Samsung Galaxy A35', src: '/img/samsungGalaxyA35.png', price: 350,  inCorzina: false, butText: "В корзину"  },
    {id: id++, name: 'iPhone 15',          src: '/img/iphone15.png',         price: 1000,  inCorzina: false, butText: "В корзину"  },
  ])

  const recieve = (obj) => {
    console.log(obj);
    counter.pushItem(obj)
  }

</script>


<template>
    <main>
      <div class="main">
        <h1>Телефоны</h1>
        <div class="tovars">
          <card 
            v-for="el in tovarList" 
            :tovar="el" 
            :key="el.id"
            @Item="recieve"
            >

          </card>
        </div>
      </div>
    </main>
</template>
  
<style>
  *{
    color:white;
  }
  h2{
    font-size: 40px;
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


  h1{
    padding-top: 300px;
  }







  .tovars{
    width: 80%;
    margin-top: 100px;
    display: flex;
    flex-wrap: wrap;
    gap: 100px;
    justify-content: center;
  }





</style>
  