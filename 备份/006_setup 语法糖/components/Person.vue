<template>
  <div class="person">
    <h2>个人信息</h2>
    <p>姓名：{{ name }}</p>
    <p>年龄：{{ age }}</p>
    <button @click="changenName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">查看联系方式</button>
  </div>
</template>

<script lang="ts" name="Person" setup>
let name = '张三'
let age = 25
let tel = '13899999999'

function showTel() {
  alert(`联系方式：${tel}`)
}
function changenName() {
  name = '李四'
  console.log(`修改后的姓名：${name}`)
}
function changeAge() {
  age += 1
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
