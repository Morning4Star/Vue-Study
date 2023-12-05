<template>
    <div>
        <h2>我是Hello组件</h2>
        <h3>我是hallo-》{{message}}->{{ msg }}->{{ number }}->{{ list }}</h3>
    </div>
</template>

<script>
export default {
    // props: ['message', 'number'],
    props: {
        message: {
            type: String,
            required: true,
            default: '我是默认值',
        },
        number: {
            type: Number,
            required: true,
            default: 0,
        },
        list: {
            type: Array,
            required: true,
            default: () => [],
        },
    },
    data() {
        return {
            msg:this.message,
            helloMsg: '我是hello组件的msg',
        }
    },
    mounted() {
        console.log(this.$root.rootmsg)
    }
}
</script>