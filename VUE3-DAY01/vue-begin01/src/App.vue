<script>
// import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      msg: '你好，Vite + Vue3',
      count: 0,
      isActive: true,
      classObj: {
        active: true,
        hh: true
      },
      error: {},
    }
  },
  methods: {
    changeActive() {
      this.isActive = !this.isActive;
    },
    changeClassObj() {
      this.classObj.active = !this.classObj.active;
      this.classObj.hh = !this.classObj.hh;
    }
  },
  computed: {
    classObjComputed() {
      return {
        active: this.isActive && !this.error,
        hh: this.error,
      }
    }
  },
  watch: {
    
  }

}
</script>


<template>
  <div>
    <p class="active">Hello Vite + Vue3</p>
    <p :class="{active:isActive}">Hello Vite + Vue3</p>
    <p :class="{active:isActive}" class="hh">Hello Vite + Vue3</p>
    <p :class="{active:isActive, hh:isActive}">Hello Vite + Vue3</p>
    <p :class="classObj">Hello Vite + Vue3</p>
    <button @click="changeActive">changeActive按钮</button>
    <button @click="changeClassObj">changeClassObj按钮</button>
    <p :class="classObjComputed">Hello Vite + Vue3</p>
  </div>
</template>

<style scoped>
.active {
  color: red;
  font-size: 50px;
}
.hh {
  font-size: 100px;
}
</style>
