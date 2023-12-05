<template>
    <div>
        <h2>我是content组件</h2>
        <Hello :message="msg" :number="aaa" :list="list" ref="hello"></Hello>
        <button @click="submitFather">向父组件提交信息</button>
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
            sonMsg:"我是content子组件组件的sonMsg",
        }
    },
    methods: {
        submitFather() {
            this.$emit('submitFatherMsg', this.sonMsg)
        }
    },
    mounted() {
        // console.log(this.$refs.hello.helloMsg)
        
    }
}
</script>