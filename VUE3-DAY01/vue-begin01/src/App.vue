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
  watch: {
    msg(newValue, oldValue) {
      console.log(newValue, oldValue);
    }
  }
}
</script>


<template>
  <div>
    <p>{{ msg }}</p>
    <button @click="changeMsg">changeMsg</button>
  </div>
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
