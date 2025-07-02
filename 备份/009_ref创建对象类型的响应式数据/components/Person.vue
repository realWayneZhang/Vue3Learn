<template>
  <div class="person">
    <h2>一辆{{ car.brand }}车，价值{{ car.price }}万</h2>
    <button @click="changePrice">修改汽车的价格</button>
    <br />
    <h2>游戏列表</h2>
    <ul>
      <li v-for="game in games" :key="game.id">{{ game.name }} - {{ game.price }}元</li>
    </ul>
    <button @click="changeFirstGameName">修改第一个游戏的名字</button>
  </div>
</template>

<script lang="ts" name="Person" setup>
import { ref, reactive } from 'vue'
// 数据
let car = ref({
  brand: '奔驰',
  price: 100,
})
let obj = reactive({ x: 999 })

console.log(1, car)
console.log(2, obj)

let games = ref([
  { id: 'game01', name: '英雄联盟', price: 100 },
  { id: 'game02', name: '王者荣耀', price: 50 },
  { id: 'game03', name: '绝地求生', price: 80 },
  { id: 'game04', name: '和平精英', price: 60 },
  { id: 'game05', name: '穿越火线', price: 30 },
  { id: 'game06', name: '使命召唤', price: 120 },
  { id: 'game07', name: 'DOTA2', price: 70 },
  { id: 'game08', name: 'GTA5', price: 150 },
  { id: 'game09', name: 'Minecraft', price: 40 },
  { id: 'game10', name: '赛博朋克2077', price: 200 },
])

function changePrice() {
  car.value.price += 10
  console.log(`修改后的汽车价格：${car.value.price}万`)
}

function changeFirstGameName() {
  games.value[0].name = '原神'
  console.log(`修改后的第一个游戏名称：${games.value[0].name}`)
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
