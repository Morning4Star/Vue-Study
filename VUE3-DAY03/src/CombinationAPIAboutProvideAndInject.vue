<script>
import { ref, provide, reactive} from 'vue';
import Content from './components/Content.vue';

export default {
  data() {
    return {}
  },
  setup() {
    let msg=ref("hello");
    
    function changeMsg() {
      msg.value="world"
    }

    function getMsgFromChild(message) {
      console.log(message.value);
    }
    const obj = reactive({
      name: "张三",
    })
    function changeObj() {
      obj.name = "王五"
    }
    provide('name',obj)

    // const name = ref("张三")
    // function changeName() {
    //   name.value = "王五"
    // }
    // provide('name',name)
    
    // return {
    //   msg, changeMsg, getMsgFromChild, changeName, name
    // }

    return {
      msg, changeMsg, getMsgFromChild, changeObj, obj
    }
  },
  components: {
    Content
  },
  mounted() {
    console.log(this.$refs.getMsgFromChildExpose.exposeValue);
  }
}
</script>

<template>
  <div>
    <Content :message="msg" @sendMsgToParent="getMsgFromChild" ref="getMsgFromChildExpose"></Content>
    <button @click="changeMsg">changeMsg</button>
  </div>
  <div>
    <h1>{{ obj.name }}</h1>
    <button @click="changeObj">changeObj</button>
  </div>
</template>

<style scoped>

</style>
    
 