<script>
//import HelloWorld from './components/HelloWorld.vue'
import Content from './components/Content.vue'
export default {
  data() {
    return {
      sonContentMsg:"",
      rootmsg:"我是App组件的rootmsg"
    }
  },
  methods: {
    getSonContentMsg(msg) {
      this.sonContentMsg = msg
    }
  },
  components: {
    Content,
  }
}
</script>

<template>
  <div>
    <h1>我是App组件</h1>
    <Content @submitFatherMsg="getSonContentMsg"></Content>
    <h2>我是App组件的sonContentMsg:{{sonContentMsg}}</h2>
  </div>
</template>

<style scoped></style>

