<template>
  <!-- 务必看懂下面这一行代码 -->
  <!-- <h2 a="1+1" :b="1 + 1" c="x" :d="x" ref="qwe">测试</h2> -->
  <Person a="哈哈" />
</template>

<script lang="ts" setup name="App">
import Person from '@/components/Person.vue'
import { reactive } from 'vue'
import type { Persons } from '@/types'

let x = 9

let personList = reactive<Persons>([
  {
    id: '001',
    name: '张三',
    age: 25,
  },
  {
    id: '002',
    name: '李四',
    age: 30,
  },
  {
    id: '003',
    name: '王五',
    age: 28,
  },
])

console.log(personList)
</script>

<style></style>
