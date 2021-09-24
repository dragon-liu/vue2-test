<template>
  <div>
    <h1 v-text="msg" ref="title"></h1>
    <button @click="getElement">点我获取上方h1元素</button>
    <school ref="sch"></school>
  </div>
</template>

<script>

import School from './components/School'

export default {
  name:'App',
  components: {
    School
  },
  data() {
    return {
      msg:'大胆学习Vue吧！'
    }
  },
  methods: {
    getElement(){
      console.log(this.$refs.title)
      console.log(this.$refs.sch)
    }
  },
}
</script>

<style scoped>

</style>
