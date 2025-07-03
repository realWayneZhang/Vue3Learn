<template>
  <Person />
</template>

<script lang="ts">
import Person from './components/Person.vue'

export default {
  name: 'App', // 组件名称
  components: {
    // 注册组件
    Person,
  },
}
</script>

<style>

</style>
