<template>
  <div class="person">
    <h1>情况四：监视上述的多个数据</h1>
    <h2>姓名：{{ person.name }}</h2>
    <h2>年龄：{{ person.age }}</h2>
    <h2>汽车：{{ person.car.c1 }} 、 {{ person.car.c2 }}</h2>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="changeCar1">修改汽车1</button>
    <button @click="changeCar2">修改汽车2</button>
    <button @click="changAllCar">修改所有车</button>
  </div>
</template>

<script lang="ts" name="Person" setup>
import { ref, reactive, toRefs, toRef, watch } from 'vue'

let person = reactive({ name: '张三', age: 25, car: { c1: '奔驰', c2: '宝马' } })

function changeName() {
  person.name += '~'
  console.log(`修改后的姓名：${person.name}`)
}
function changeAge() {
  person.age += 1
  console.log(`修改后的年龄：${person.age}`)
}
function changeCar1() {
  person.car.c1 = '奥迪'
  console.log(`修改后的汽车1：${person.car.c1}`)
}
function changeCar2() {
  person.car.c2 = '特斯拉'
  console.log(`修改后的汽车2：${person.car.c2}`)
}
function changAllCar() {
  person.car = { c1: '法拉利', c2: '兰博基尼' }
  console.log(`修改后的汽车：${person.car.c1} 、 ${person.car.c2}`)
}

// watch(person, (newValue, oldValue) => {
//   console.log('person 属性发生变化：', newValue, oldValue)
// })

// 监视，情况五：监视上述的多个数据
watch(
  [() => person.name, () => person.car.c1],
  (newValue, oldValue) => {
    console.log('person 属性发生变化：', newValue, oldValue)
  },
  { deep: true }, // 深度监视 person.car 对象的变化
)
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
