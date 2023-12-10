<script>
import { h, ref,toRefs, inject, onMounted, onUpdated ,onBeforeUpdate} from 'vue'
export default {
  data() {
    return {
      
    }
  },
  props: {
    message: {
      type: String,
      default: "hello"
    }
  },
  setup(props, Content) {
    const msg = toRefs(props).message
    const message = ref("Content组件的message属性值")
    const exposeValue = ref("暴露给父组件的值")
    const name = inject("name")
    Content.expose({
        exposeValue
        
    })
    function sendMsgToParent() {
      Content.emit("sendMsgToParent", message)
    }
    onMounted(() => {
      console.log(name.value);
    })
    onUpdated(() => {
      console.log(name.value);
    })

    onBeforeUpdate(() => {
      console.log(name.value);
    })
    // return () => h('div', [h('h1', msg.value), h('button', {onClick: sendMsgToParent}, {default: () => 'sendMsgToParent'})])
    return {
      msg, sendMsgToParent, name
    }
  },
}
</script>

<template>

    <div>
        <h1>{{ msg }}</h1>
        <button @click="sendMsgToParent">sendMsgToParent</button>
    </div>
    <div>
        <h1>{{ name.name }}</h1>
    </div>
</template>