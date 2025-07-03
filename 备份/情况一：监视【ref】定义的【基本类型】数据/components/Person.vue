<template>
  <div class="person">
    <h1>情况一：监视【ref】定义的【基本类型】数据</h1>
   <h2>当前求和为：{{sum}}</h2>
   <button @click="changeSum">点我 sum+1</button>
  </div>
</template>

<script lang="ts" name="Person" setup>
import { ref, reactive, toRefs, toRef, watch } from 'vue'
// 数据
let sum = ref(0)

function changeSum() {
  sum.value += 1
  console.log(`修改后的求和：${sum.value}`)
}

// 监视
const stopWatch = watch(sum, (newValue, oldValue) => {
  console.log(`求和从 ${oldValue} 变为 ${newValue}`)
  if (newValue > 10) {
    console.log('求和超过10，停止监视')
    stopWatch() // 停止监视
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
