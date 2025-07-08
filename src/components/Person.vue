<template>
  <div class="person">
    <h2>当前求和为: {{ sum }}</h2>
    <button @click="add">点我 sum+1</button>
  </div>
</template>

<script lang="ts" setup name="Person">
import {
  ref,
  onBeforeMount,
  onMounted,
  onBeforeUpdate,
  onUpdated,
  onBeforeUnmount,
  onUnmounted,
} from 'vue'
let sum = ref(0)

function add() {
  sum.value += 1
}

// 创建
console.log('Person组件被创建了')
// 挂载前
onBeforeMount(() => {
  console.log('Person组件挂载前')
})
// 挂载后
onMounted(() => {
  console.log('Person组件挂载后')
})
// 更新前
onBeforeUpdate(() => {
  console.log('Person组件更新前')
})
// 更新后
onUpdated(() => {
  console.log('Person组件更新后')
})

// 卸载前
onBeforeUnmount(() => {
  console.log('Person组件卸载前')
})
// 卸载后
onUnmounted(() => {
  console.log('Person组件卸载后')
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
