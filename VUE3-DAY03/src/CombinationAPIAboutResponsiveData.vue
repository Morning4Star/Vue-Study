<script>
import { ref , reactive, watch, watchEffect, computed} from 'vue'

export default {
  
  data() {
    return {

    }
  },
  setup() {
    
    let number = ref(0);
    function changeNumber() {
      number.value++
    }
    const obj = reactive({
      name: "张三",
      age: 18,
    })
    function changeObj() {
      obj.name = "王五"
    }
    watch(number,(newValue, olderValue)=> {
      console.log(newValue, olderValue);
    })
    
    watchEffect(()=> {
      console.log(obj.name);
    })

    const msg = ref("hello");
    const reverseMsg = computed(() => {
      return msg.value.split('').reverse().join('')
    })
    console.log(reverseMsg.value);

    return {
      number, changeNumber, obj, changeObj, msg, reverseMsg
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
    <h1>{{ obj.name }}</h1>
    <button @click="changeObj">changeObj</button>
  </div>
  <div>
    <h1>{{ reverseMsg }}</h1>
  </div>
</template>

<style scoped>

</style>
