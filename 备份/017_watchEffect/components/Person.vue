<template>
  <div class="person">
    <h2>需求：当水温达到 60 度或水位达到 80cm，给服务器发请求</h2>
    <h2>当前水温：{{ temp }}</h2>
    <h2>当前水位：{{ height }}</h2>
    <button @click="changeTemp">水温+10</button>
    <button @click="changeHeight">水位+10</button>
  </div>
</template>

<script lang="ts" name="Person" setup>
import { ref, reactive, toRefs, toRef, watch, watchEffect } from 'vue'

let temp = ref(0)
let height = ref(0)
function changeTemp() {
  temp.value += 10
  console.log(`修改后的水温：${temp.value}`)
}
function changeHeight() {
  height.value += 10
  console.log(`修改后的水位：${height.value}`)
}

// watch([temp, height], ([newTemp, newHeight], [oldTemp, oldHeight]) => {
//   if (newTemp >= 60 || newHeight >= 80) {
//     console.log(`水温或水位达到阈值，发送请求：水温=${newTemp}，水位=${newHeight}`)
//     // 在这里可以添加发送请求的逻辑
//   } else {
//     console.log(`水温或水位未达到阈值：水温=${newTemp}，水位=${newHeight}`)
//   }
// })

// 使用 watchEffect 监视多个响应式数据
watchEffect(() => {
  if (temp.value >= 60 || height.value >= 80) {
    console.log(`水温或水位达到阈值，发送请求：水温=${temp.value}，水位=${height.value}`)
    // 在这里可以添加发送请求的逻辑
  } else {
    console.log(`水温或水位未达到阈值：水温=${temp.value}，水位=${height.value}`)
  }
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
