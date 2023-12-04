<script>
//import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      count: 0,
      msg: 'Hello Vue3',
      checked: "",
      fruit: [],
      sex: "",
      city: "",
      citys: [],
      msgLazy: "",
      msgNumber: "",
      msgTrim: "",
    }
  },
  methods: {
    changeMsg(event) {
      this.msg = event.target.value;
    },
    inputTrim(event) {
      console.log(event.target.value);
    },

  }
}
</script>

<template>
  <div>
        <input type="text" v-model="msg">
        <p>{{ msg }}</p>
    <input type="text" :value="msg" @input="changeMsg">
   
  </div>
  <div>
    <input type="checkbox" v-model="checked">
    <p>{{ checked }}</p>
  </div>
  <div>
    <!-- 多个复选框 -->
    <input type="checkbox" value="西瓜" v-model="fruit">西瓜
    <input type="checkbox" value="香蕉" v-model="fruit">香蕉
    <input type="checkbox" value="苹果" v-model="fruit">苹果
    <input type="checkbox" value="橘子" v-model="fruit">橘子
    <input type="checkbox" value="梨子" v-model="fruit">梨子
    <h1>你选择的水果是：{{ fruit }}</h1>
  </div>
  <div>
    <!-- 单选框 -->
    <input type="radio" value="男" v-model="sex">男
    <input type="radio" value="女" v-model="sex">女
    <h1>你选择的性别是：{{ sex }}</h1>
  </div>
  <div>
    <!-- 下拉列表,单选 -->
    <select name="" id="" v-model="city">
      <option value="北京">北京</option>
      <option value="上海">上海</option>
      <option value="广州">广州</option>
      <option value="深圳">深圳</option>
      <option value="杭州">杭州</option>
    </select>
    <h1>你选择的城市是：{{ city }}</h1>
  </div>
  <div>
    <!-- 下拉列表，多选 -->
    <select name="" id="" v-model="citys" multiple>
      <option value="北京">北京</option>
      <option value="上海">上海</option>
      <option value="广州">广州</option>
      <option value="深圳">深圳</option>
      <option value="杭州">杭州</option>
    </select>
    <h1>你选择的城市是：{{ citys }}</h1>
  </div>
  <div>
    <!-- input.lazy -->
    <input type="text" v-model.lazy="msgLazy">
    <h2>{{ msgLazy }}</h2>
  </div>
  <div>
    <!-- .number -->
    <input type="text" v-model.number="msgNumber">
    <h2>{{ typeof msgNumber }}</h2>
  </div>
  <div>
    <!-- .trim -->
    <input tpye="text" v-model.trim="msgTrim" @keyup="inputTrim">
    <h2>{{ msgTrim }}</h2>
  </div>
</template>

<style scoped></style>

