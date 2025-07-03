<template>
  <div class="person">
    <h1>情况二：监视【ref】定义的【对象类型】数据</h1>
    <h2>姓名：{{ person.name }}</h2>
    <h2>年龄：{{ person.age }}</h2>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="changePerson">修改人</button>
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

function changePerson() {
  person.value = { name: '李四', age: 30 }
  console.log(`修改后的姓名：${person.value.name}, 年龄：${person.value.age}`)
}

// 监视 person 对象的变化， 监视【ref】定义的【对象类型】数据，监视的对象的地址值，若想监视对象内部属性的变化，需要开启深度监视，设置 { deep: true }
// watch 的第一个参数是：被监视的数据
// watch 的第二个参数是：回调函数，回调函数的第一个参数是新值，第二个参数是旧值
// watch 的第三个参数是：配置项，开启深度监视（deep、immediate）等等......
watch(
  person,
  (newValue, oldValue) => {
    console.log('person 对象发生变化：', newValue, oldValue)
  },
  { deep: true },
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
