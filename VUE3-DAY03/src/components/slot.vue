<template>
    <div>
        <h1>我是content组件</h1>
        <h1>----------------------</h1>
        <slot name="a">
            <button>默认按钮</button>
        </slot>
        <slot name="b"></slot>
        <slot name="c" :list="list"></slot>
        <h1>----------------------</h1>
    </div>
</template>

<script>
export default {
    data() {
        return {
            contentMsg: '我是content组件的contentMsg',
            list:[1,4,2,5,6,3,7,8,9,0]
        }
    },
    methods: {

    },
    components: {

    }
}
</script>