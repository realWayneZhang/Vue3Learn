<template>
  <div class="person">
   <h2>姓名：{{name}}</h2>
   <h2>年龄：{{age}} {{nl}}</h2>
   <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
  </div>
</template>

<script lang="ts" name="Person" setup>
import { ref, reactive, toRefs, toRef } from 'vue'

// 数据
let person = reactive({name: '张三', age: 25})

let {name, age} = toRefs(person);
let nl = toRef(person, 'age');
console.log(`姓名：${name}, 年龄：${age}`)
console.log(`年龄：${nl.value}`)

// 方法
function changeName() {
  name.value += '~'
  console.log(`修改后的姓名：${name.value}`)
}
function changeAge() {
  age.value += 1
  console.log(`修改后的年龄：${age.value}`)
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
