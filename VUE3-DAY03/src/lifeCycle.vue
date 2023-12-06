<script>
import Hello from './components/Hello.vue';
export default {
  data() {
    return {
      isShow: true,
    }
  },
  methods: {
    
  },
  components: {
    Hello,
},
  mounted() {
    
  }
}
</script>

<template>
  <div>
    <Hello v-if="isShow"></Hello>
    <button @click="isShow=!isShow">取反isShow</button>
  </div>
  <div>
    
  </div>
</template>

<style scoped>

</style>
