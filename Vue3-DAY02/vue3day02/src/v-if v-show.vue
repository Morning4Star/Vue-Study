<script>
//import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      isAdult: false,
      age: 18,
      isMan: false,
    }
  },
  methods: {
    changeSex() {
      this.isMan = !this.isMan;
    }
  },
  watch: {
    // 大于18岁显示你已经成年了，等于18岁刚好成年,小于18岁显示你还未成年
    age(newValue, oldValue) {
      if (newValue < 0) {
        this.age = 0;
      } else if (newValue > 18) {
        this.isAdult = true;
      } else if (newValue == 18) {
        this.isAdult = false;
      } else {
        this.isAdult = false;
      }
    }
  }
}
</script>

<template>
  <div>
    <p v-if="isAdult">你已经成年了</p>
    <p v-else-if="age==18">刚好成年</p>
    <p v-else>你还未成年</p>
    <input type="text" v-model="age">
    <template v-if="isAdult">
      <p>18禁</p>
      <p>18禁</p>
      <p>18禁</p>
      <p>18禁</p>
      <p>18禁</p>
      <p>18禁</p>
    </template>
    <p v-show="isMan">男生</p>
    <p v-show="!isMan">女生</p>
    <button @click="changeSex">改变性别</button>
  </div>
</template>

<style scoped>
</style>
