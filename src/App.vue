<template>
  <!-- 务必看懂下面这一行代码 -->
  <!-- <h2 a="1+1" :b="1 + 1" c="x" :d="x" ref="qwe">测试</h2> -->
  <button @click="show">切换显示</button>
  <Person a="哈哈" v-if="isShow" />
</template>

<script lang="ts" setup name="App">
import Person from '@/components/Person.vue'
import { ref } from 'vue'

let isShow = ref(true)

function show() {
  isShow.value = !isShow.value
}
</script>

<style></style>
