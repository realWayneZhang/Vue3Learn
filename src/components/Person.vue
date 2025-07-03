<template>
  <div class="person">
    <h1>情况二：监视【ref】定义的【对象类型】数据</h1>
    <h2>姓名：{{ person.name }}</h2>
    <h2>年龄：{{ person.age }}</h2>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
  </div>
</template>

<script lang="ts" name="Person" setup>
import { ref, reactive, toRefs, toRef, watch } from 'vue'
let person = ref({ name: '张三', age: 25 })

function changeName() {
  person.value.name += '~'
  console.log(`修改后的姓名：${person.value.name}`)
}
function changeAge() {
  person.value.age += 1
  console.log(`修改后的年龄：${person.value.age}`)
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
