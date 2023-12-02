<script>
// import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      msg: '你好，Vite + Vue3',
      count: 0,
      user: {
        name: '张三',
        age: 18
      }
    }
  },
  methods: {
    changeMsg() {
      this.msg = '你好，Vite + Vue3' + this.count++;
    },
    changeUser() {
      this.user.name = '李四';
      this.user.age = 20;
      // this.user = {
      //   name: '李四',
      //   age: 20
      // }
    }
  },
  watch: {
    // msg(newValue, oldValue) {
    //   console.log(newValue, oldValue);
    //   if (newValue.length > 10 || newValue.length < 5) {
    //     console.log('长度不符合要求');
    //   }
    // }
    msg: {
      immediate: true,//立即执行
      handler(newValue, oldValue) {
        console.log(newValue, oldValue);
        if (newValue.length > 10 || newValue.length < 5) {
          console.log('长度不符合要求');
        }
      }
    },
    // user: {
    //   handler(newValue, oldValue) {
    //     console.log(newValue, oldValue);
    //   },
    //   deep: true//深度监听
    // }
    'user.name': {
      handler(newValue, oldValue) {
        console.log(newValue, oldValue);
      },
      deep: true//深度监听
    }
  }

}
</script>


<template>
  <div>
    <p>{{ msg }}</p>
    <button @click="changeMsg">changeMsg</button>
    <p>{{ user.name }}</p>
    <p>{{ user.age }}</p>
    <input type="text" v-model="msg">
    <button @click="changeUser">changeUser</button>

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
