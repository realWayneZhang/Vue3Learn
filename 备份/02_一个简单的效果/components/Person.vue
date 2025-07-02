<template>
  <div class="person">
    <h2>个人信息</h2>
    <p>姓名：{{ name }}</p>
    <p>年龄：{{ age }}</p>
    <button @click="changenName">修改名字</button>
    <button @click="changeAge">修改年龄</button>
    <button @click="showTel">查看联系方式</button>
  </div>
</template>

<script lang="ts">
export default {
  name: 'Person',
  data() {
    return {
      name: '张三',
      age: 25,
      tel: '13899999999',
    }
  },
  methods: {
    showTel() {
      alert(`联系方式：${this.tel}`)
    },
    changenName() {
      this.name = '李四'
    },
    changeAge() {
      this.age = 30
    },
  },
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
