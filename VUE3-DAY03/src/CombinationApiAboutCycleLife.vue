<script>
import { onBeforeMount, onMounted, onBeforeUpdate, onUpdated, reactive,} from 'vue'

export default {
  data() {
    return {}
  },
  setup() {

    const obj = reactive({
      name: "张三",
      age: 18,
    })
    function changeObj() {
      obj.name = "王五"
    }

    onBeforeMount(() => {
      console.log("onBeforeMount");
    })

    onMounted(() => {
      console.log("onMounted");
    })

    onBeforeUpdate(() => {
      console.log("onBeforeUpdate");
    })

    onUpdated(() => {
      console.log("onUpdated");
    })

  
    return {
      obj, changeObj
    }
  },
}
</script>

<template>
  <div>
    <h1>{{ obj.name }}</h1>
    <button @click="changeObj">changeObj</button>
  </div>
</template>

<style scoped>

</style>
    
 