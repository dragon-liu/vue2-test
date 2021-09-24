<template>
  <div class="student">
      <h2>姓名:{{name}}</h2>
      <h2>年龄:{{age}}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
        name:'ZionLong',
        age:22
    }
  }
}
</script>

<style scoped>
.student{
    background-color: aquamarine;
}
</style>
