<template>
    <div>
        <h1>
            {{ msg }}
        </h1>
        <button @click="msg++">msg++</button>
    </div>
</template>

<script>

export default {
    data() {
        return {
            msg : 0,
        }
    },
    beforeCreate() {
        console.log("beforeCreate");
    },
    created() {
        console.log("Created");
    },
    beforeMount() {
        console.log("beforeMount");
    },
    mounted() {
        console.log("mounted");
    },
    beforeUpdate() {
        console.log("beforeUpdate");
    },
    updated() {
        console.log("update");
    },
    beforeUnmount() {
        console.log("beforeUnmount");
    },
    unmounted() {
        console.log("unmounted");
    },
}
</script>