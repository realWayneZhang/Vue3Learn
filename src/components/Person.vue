<template>
  <div class="person">
    <h2>一辆{{ car.brand }}车，价值{{ car.price }}万</h2>
    <button @click="changePrice">修改汽车的价格</button>
    <h2>当前求和为{{ sum }}</h2>
    <button @click="changeSum">点我 sum+1</button>
  </div>
</template>

<script lang="ts" name="Person" setup>
import { ref, reactive } from 'vue'
// 数据
let car = ref({
  brand: '奔驰',
  price: 100,
})
let sum = ref(0)

function changeSum() {
  sum.value += 1
  console.log(`修改后的求和：${sum.value}`)
}

function changePrice() {
  car.value.price += 10
  console.log(`修改后的汽车价格：${car.value.price}万`)
}
</script>

<style scoped>
.person {
  background-color: skyblue;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px;
  margin: 10px 0;
}
</style>
