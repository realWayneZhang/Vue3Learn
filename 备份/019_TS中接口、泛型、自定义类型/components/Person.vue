<template>
  <div class="person">
    
  </div>
</template>

<script lang="ts" setup name="Person">
import { type PersonInterface, type Persons } from '@/types'

// let person: PersonInterface = {
//   id: '001',
//   name: '张三',
//   age: 25
// }

let personList: Persons = [
  {
    id: '001',
    name: '张三',
    age: 25
  },
  {
    id: '002',
    name: '李四',
    age: 30
  }
]

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
