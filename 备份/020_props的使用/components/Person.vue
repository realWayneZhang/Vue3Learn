<template>
  <div class="person">
    <ul>
      <li v-for="item in list" :key="item.id">{{ item.name }} - {{ item.age }}</li>
    </ul>
  </div>
</template>

<script lang="ts" setup name="Person">
import type { Persons } from '@/types'

// 接收a
// defineProps(['a'])

// 接收a和 list，同时将 props 保存起来
// const props = defineProps(['a', 'list'])

// 接收 list +限制类型
// const props = defineProps<{ list: Persons }>()

// 接收限制类型 + 限制类型 + 限制必要性 + 指定默认值
const props = withDefaults(defineProps<{ list?: Persons }>(), {
  list: () => [{ id: '001', name: '康师傅·王麻子·特仑苏', age: 40 }],
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
