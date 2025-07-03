<template>
  <div class="person">
    <h1>情况三：监视【reactive】定义的【对象类型】数据</h1>
    <h2>姓名：{{ person.name }}</h2>
    <h2>年龄：{{ person.age }}</h2>
    <button @click="changeName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="changePerson">修改人</button>
    <hr />
    <h2>测试：{{ obj.a.b.c }}</h2>
    <button @click="() => obj.a.b.c++">修改 obj.a.b.c</button>
  </div>
</template>

<script lang="ts" name="Person" setup>
import { ref, reactive, toRefs, toRef, watch } from 'vue'
let person = reactive({ name: '张三', age: 25 })

let obj = reactive({ a: { b: { c: 666 } } })

function changeName() {
  person.name += '~'
  console.log(`修改后的姓名：${person.name}`)
}
function changeAge() {
  person.age += 1
  console.log(`修改后的年龄：${person.age}`)
}

function changePerson() {
  Object.assign(person, { name: '李四', age: 30 })
  console.log(`修改后的姓名：${person.name}, 年龄：${person.age}`)
}

/*
  情况三：监视【reactive】定义的【对象类型】数据，且默认是开启深度监视的
*/
watch(person, (newValue, oldValue) => {
  console.log('person 对象发生变化：', newValue, oldValue)
})

watch(obj, (newValue, oldValue) => {
  console.log('obj 对象发生变化：', newValue, oldValue)
})
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
