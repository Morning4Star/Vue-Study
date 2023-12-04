<template>
    <div>
        <h2>我是content组件</h2>
        <Hello :message="msg" :number="aaa" :list="list"></Hello>
        
    </div>
</template>

<script>
import Hello from './Hello.vue'
export default {
    components: {
        Hello,
    },
    data() {
        return {
            msg: '我是content组件Msg',
            list: ['a', 'b', 'c'],
        }
    },
}
</script>