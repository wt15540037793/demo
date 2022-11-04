<template>
  <div class="container">
    <!-- <h1>父组件</h1>
    <p>{{money}}</p>
    <hr>
    <Son :money="money" @change-money="updateMoney"></Son> -->
    <h1>父组件{{money}}<button @click="money=100">发钱</button></h1>
    <hr>
    <Son/>
  </div>
</template>

<script>
import {ref} from 'vue'
import Son from '../components/Son.vue'
export default {
  name: 'HomeView',
  components: {
    Son
  },
  //父组件的数据传递给数据
  setup(){
    const money=ref(100)
    const changeMoney=(saleMoney)=>{
      console.log('changeMoney',saleMoney);
      money.value=money.value-saleMoney
    }
    //将数据提供给后代组件 provide
    provide('money',money)
    //将函数提供给后代组件 provide
    provide('changeMoney',changeMoney)
    return {money}

    // const updateMoney=(newMoney)=>{
    //   money.value=newMoney
    // }
    // return {money,updateMoney}
  }
}
</script>
