<script>
export default {
    //   inject: ['message']
    inject: ["grandFatherObj","grandFatherMessage"]
}
</script>

<template>
    <h1>
        Son  ===>  {{ grandFatherObj.msg }},{{ grandFatherMessage() }}
    </h1>
</template>