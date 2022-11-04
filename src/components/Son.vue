<template>
    <div class="container">
        <!-- <h1>子组件</h1>
        <p>{{money}}</p>
        <button @click="changeMoney">一天花60元</button> -->

        <h2>子组件{{money}}</h2>
        <hr>
        <GrandSon></GrandSon>
    </div>
</template>

<script>
// import { onMounted } from 'vue';
import {inject} from 'vue'
import GrandSon from '../components/GrandSon.vue'
export default {
    name:'Son',
    components:{GrandSon},
    setup(){
        //接受祖先组件提供的数据
        const money=inject('money')
        return {money}
    }

    // //子组件接受父组件数据使用props即可
    // pops:{
    //     money:{
    //         type:Number,
    //         default:0
    //     }
    // },
    // //props父组件数据
    // //emit触发自定义事件的函数
    // setup (props,emit) {
    //     //获取父组件数据money
    //     console.log(props.money);
    //     //向父组件传值
    //     const changeMoney=()=>{
    //         //消费60元
    //         //通知父组件，money需要变成60
    //         emit('change-money',60)
    //     }
    //     return {changeMoney}
    // }
}
</script>

<style lang="scss" scoped>

</style>