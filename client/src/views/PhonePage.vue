<script>
  import { mapActions, mapState } from 'pinia';
  import { useCounterStore } from '../stores/counter';
  import CardPhone from '../components/CardPhones.vue'

  export default {
    components: {
      CardPhone
    },
    methods: {
      ...mapActions(useCounterStore, ['fetchDataPhone'])
    },
    computed: {
      ...mapState(useCounterStore, ['phone', 'isLogin'])
    },
    created() {
      this.fetchDataPhone()
    }
  }
</script>

<template>
    <!--home-->
  <div class="mt-4" style="background-color: white; ">
    <div class="container text-center">
      <h1>RentOPhone</h1>
      </div>
      <div class="container text-left">
      <p>Kamu pasti pernah melihat salah satu artis favorit kamu ataupun artis dunia terkenal yang menggunakan iPhone. iPhone merupakan salah satu produk smartphone yang dikeluarkan oleh Apple, raksasa teknologi dari Amerika Serikat. Seiring dengan perkembangannya, banyak sekali jenis-jenis smartphone dari Apple yang dijual di pasaran sejak perilisan pertamanya di tahun 2007. Namun memang harga dari produk buatan Apple ini tidak murah, eits! tapi tenang kini kamu bisa menggunakan Iphone dengan menyewa nya saja.</p>
      <p v-if="!isLogin" class="container text-center" style="color: red;">**Register for purchasing**</p>
  </div>
</div>
<div class="container" style="margin-top:50px;">
  <div class="row" >
    <CardPhone v-for="item in phone" :key="item.id" :item="item" />
  </div>  
</div>  
</template>

<style>
    /* stylingCard */
  /*  Helper Styles */
  body {
    font-family: Varela Round;
    background: #f1f1f1;
  }

  a {
    text-decoration: none;
  }

  /* Card Styles */

  .card-sl {
    border-radius: 8px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
  }

  .card-image img {
    max-height: 100%;
    max-width: 100%;
    border-radius: 8px 8px 0px 0;
  }

  .card-action {
    position: relative;
    float: right;
    margin-top: -25px;
    margin-right: 20px;
    z-index: 2;
    color: #E26D5C;
    background: #fff;
    border-radius: 100%;
    padding: 15px;
    font-size: 15px;
    box-shadow: 0 1px 2px 0 rgba(0, 0, 0, 0.2), 0 1px 2px 0 rgba(0, 0, 0, 0.19);
  }

  .card-action:hover {
    color: #fff;
    background: #E26D5C;
    -webkit-animation: pulse 1.5s infinite;
  }

  .card-heading {
    font-size: 18px;
    font-weight: bold;
    background: #fff;
    padding: 10px 15px;
  }

  .card-text {
    padding: 10px 15px;
    background: #fff;
    font-size: 14px;
    color: #636262;
  }

  .card-button2 {
    display: flex;
    justify-content: center;
    padding: 10px 0;
    width: 100%;
    background-color: #1F487E;
    color: #fff;
    border-radius: 0 0 10px 10px;
  }

  .card-button {
    display: flex;
    justify-content: center;
    padding: 10px 0;
    width: 100%;
    background-color: #1F487E;
    color: #fff;
  }

  .card-button:hover {
    text-decoration: none;
    background-color: #1D3461;
    color: #fff;

  }


  @-webkit-keyframes pulse {
    0% {
      -moz-transform: scale(0.9);
      -ms-transform: scale(0.9);
      -webkit-transform: scale(0.9);
      transform: scale(0.9);
    }

    70% {
      -moz-transform: scale(1);
      -ms-transform: scale(1);
      -webkit-transform: scale(1);
      transform: scale(1);
      box-shadow: 0 0 0 50px rgba(90, 153, 212, 0);
    }

    100% {
      -moz-transform: scale(0.9);
      -ms-transform: scale(0.9);
      -webkit-transform: scale(0.9);
      transform: scale(0.9);
      box-shadow: 0 0 0 0 rgba(90, 153, 212, 0);
    }
  }
  /* endStylingCard */
</style>