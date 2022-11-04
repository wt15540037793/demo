<template>
    <div class="container">
        <h3>孙组件{{money}}<button @click="fn">消费20</button></h3>
    </div>
</template>

<script>
import {inject} from 'vue'
export default {
    name:'GrandSon',
    setup () {
        //孙组件，消费60，通知父组件，进行修改
        //不能自己修改数据，遵循单选数据流原则，大白话：数据谁定义谁修改
        const changeMoney=inject('changeMoney')
        const fn=()=>{
            changeMoney(20)
        }
        return {money,fn}
    }
}
</script>

<style lang="scss" scoped>

</style>