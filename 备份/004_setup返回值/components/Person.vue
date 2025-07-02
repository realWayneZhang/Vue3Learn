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
  beforeCreate() {
    console.log('beforeCreate: 组件即将被创建')
  },

  setup() {
    // 数据，原来是写在 data 中，此时的 name、age 和 tel 都不是响应式的
    let name = '张三'
    let age = 25
    let tel = '13899999999'

    // 方法
    function showTel() {
      alert(`联系方式：${tel}`)
    }
    function changenName() {
      name = '李四' // 注意：这样修改 age，页面是没有变化的
      console.log(`修改后的姓名：${name}`) // 这里可以看到修改后的值
    }
    function changeAge() {
      age += 1 // 注意：这样修改 age，页面是没有变化的
      console.log(`修改后的年龄：${age}`) // 这里可以看到修改后的
    }

    // 返回值，这些值会被暴露到模板中
    return {
      name,
      age,
      tel,
      showTel,
      changenName,
      changeAge,
    }

    // setup 的返回值也可以是一个渲染函数
    return () => '哈哈'
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
