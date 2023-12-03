<script>
//import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      count: 0,
      age: 18,
    }
  },
  methods: {
    addCounter(number, event) {
      this.count += number;
      console.log(event);
    },
    addAge(number, event) {
      this.age += number;
      console.log(event);
    },
    fatherClick() {
      console.log('fatherClick');
    },
    sonClick() {
      console.log('sonClick');
    },
    submit() {
      alert('submit');
    },
    onceClick() {
      alert('onceClick');
    },
    enterClick() {
      alert('enterClick');
    },
  }
}
</script>

<template>
  <div>
    <p @click="addCounter">{{ count }}</p>
    <p @click="addCounter(5)">{{ count }}</p>
    <!-- 绑定参数，既传递参数，又要有事件对象 -->
    <h2 @click="addCounter(5, $event)">{{ count }}</h2>
    <h2 @click="addCounter(1, $event), addAge(1, $event)">{{ count }}, {{ age }}</h2>
    <!-- 事件修饰符 -->
    <!-- .stop -->
    <div @click="fatherClick">
      <button @click.stop="sonClick">按钮</button>
    </div>
    <!-- .prevent -->
    <form action="http://www.baidu.com" method="get" @submit="submit">
      <input type="text" name="username">
      <input type="submit" value="提交" @click="submitClick">
    </form>
    <!-- .once -->
    <button @click.once="onceClick">按钮</button>
    <!-- .{keyCode} || keyAlias -->
    <div>
      <input type="text" @keyup.enter="enterClick">
    </div>

  </div>
</template>

<style scoped></style>
