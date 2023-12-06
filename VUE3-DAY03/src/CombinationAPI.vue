<script>
import { ref } from 'vue'
import { reactive, toRefs} from 'vue'
export default {
  data() {
    return {

    }
  },
  setup() {
    const msg = ref(0);
    function changeMsg() {
      msg.value++
    }

    let number = 0;
    function changeNumber() {
      number++
    }

    let obj = reactive({
      name: "张三",
      age: 18,
      Children: {
        name: "李四",
        age: 20
      }
    })
    function changeObj() {
      obj.name = "王五"
    }
    return {
      msg,
      changeMsg,
      number,
      changeNumber,
      obj,
      changeObj,
      ...toRefs(obj)
    }

  }
  ,
  methods: {
    
  },
}
</script>

<template>
  <div>
    <h1>{{ number }}</h1>
    <button @click="changeNumber">changeNumber</button>
    <h1>{{ msg }}</h1>
    <button @click="changeMsg">changeMsg</button>
    <h1>{{ obj.name }}</h1>
    <h1>{{ name }}</h1>
    <button @click="changeObj">changeObj</button>
  </div>
</template>

<style scoped>

</style>
