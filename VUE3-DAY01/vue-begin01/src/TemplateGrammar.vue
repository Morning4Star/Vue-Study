<script>
// import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      msg: 'Vite + Vue',
      count: 0,
      message:"<h1>hello</h1>",
      id: "d2",
    }
  },
  methods: {
    changeMsg() {
      this.msg = 'Vite + Vue' + this.count++
    },
    changeId() {
      this.id = this.id === "d1" ? "d2" : "d1";
    },
  }
}
</script>


<template>
  <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
    <p>{{ msg }}</p>
    <p v-once>{{ msg }}</p>
    <p>{{ message }}</p>
    <p v-html="message"></p>
    <button @click="changeMsg">改变msg</button>
    <p v-bind:id="id">v-bind绑定</p>
    <button @click="changeId">切换id</button>
    <button @click="id = id === 'd1' ? 'd2' : 'd1'">切换id</button>
    <p>{{ count + 1 }}</p>
    <!-- 翻转 -->
    <p>{{ msg.split('').reverse().join('') }}</p>
    <p v-bind:id="id+2">v-bind绑定</p>
    <!-- 语法糖:-->
    <p :id="id">v-bind绑定</p>
    <!-- v-on 监听 DOM 事件 -->
    <button v-on:click="changeMsg">改变msg</button>
    <!-- v-on语法糖: @ -->
    <button @click="changeMsg">改变msg</button>
  </div>
  <HelloWorld msg="Vite + Vue" />
</template>

<style scoped>
#d1 {
  color: blue;
}

#d2 {
  color: red;
}
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
