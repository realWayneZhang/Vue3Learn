<template>
  <div class="person">
    <h2>个人信息</h2>
    <p>姓名：{{ name }}</p>
    <p>年龄：{{ age }}</p>
    <p>地址：{{ address }}</p>
    <button @click="changenName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">查看联系方式</button>
  </div>
</template>

<script lang="ts" name="Person" setup>
import { ref } from 'vue'
let name = ref('张三')
let age = ref(25)
let tel = ref('13899999999')
let address = '北京市昌平区宏福苑·宏福科技园'

console.log(1, name)
console.log(2, age)
console.log(3, tel)

function showTel() {
  alert(`联系方式：${tel.value}`)
}
function changenName() {
  name.value = '李四'
  console.log(`修改后的姓名：${name.value}`)
}
function changeAge() {
  age.value += 1
  console.log(`修改后的年龄：${age}`)
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
