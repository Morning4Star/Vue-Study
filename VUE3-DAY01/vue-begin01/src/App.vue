<script>
// import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      msg: '你好，Vite + Vue3',
      count: 0,
      activeColor: 'red',
      fontSize: 50,
      classObj:{
        fontSize:'100px',
        color:'red',
        backgroundColor:'green'
      }
    }
  },
  methods: {

  },
  computed: {

  },
  watch: {

  }

}
</script>
  
<template>
  <div>
    <p style="color:red">{{ msg }}</p>
    <p :style="{ color: activeColor, fontSize: fontSize + 'px' }">{{ msg }}</p>
    <p :style="{ color: activeColor, 'font-size': fontSize + 'px' }">{{ msg }}</p>
    <p :style=classObj>{{ msg }}</p>
    <p :style="[classObj, {borderColor:'red'}]">{{ msg }}</p>

  </div>
</template>

<style scoped>
</style>
