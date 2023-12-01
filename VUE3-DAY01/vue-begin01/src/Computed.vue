<script>
// import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      msg: 'Vite + Vue',
      count: 0,
    }
  },
  methods: {
    changeMsg() {
      this.msg = 'Vite + Vue' + this.count++;
    }
  },
  computed: {
    //简写
    // reverseMsg() {
    //   return this.msg.split('').reverse().join('');
    // }
    //完整写法
    reverseMsg: {
      set:function(newValue) {
        console.log(newValue);
        this.msg = newValue;
        console.log(this.msg);
      },
      get() {
        return this.msg.split('').reverse().join('');
      },

    }
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
  </div>
  <p>{{ reverseMsg }}</p>
  <p>{{ msg }}</p>
  <button @click="changeMsg">更改Msg</button>
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
}</style>
