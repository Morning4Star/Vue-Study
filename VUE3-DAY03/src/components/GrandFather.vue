<script>
import Father from './Father.vue'

export default {
    data() {
        return {
            grandFatherMsg: "this is GrandFatherMsg",
            grandFatherObj:{
                msg:"this is GrandFatherMsg",
            }
        }
    },
    methods:{
        changeMsg() {
            this.grandFatherObj.msg = "this is GrandFatherMsg!!"
            this.grandFatherMsg = "this is GrandFatherMsg!!"
        }
    },
    components: { Father },
      provide(){
        return {
            grandFatherObj:this.grandFatherObj,
            grandFatherMessage:()=>this.grandFatherMsg
        }
      },

    // provide: {
    //     message: "this is GrandFatherMsg"
    // }
}
</script>

<template>
    <h1>GrandFather  ==》 {{ grandFatherObj.msg }},{{ grandFatherMsg }}</h1>
    <div>
        <button @click="changeMsg">改变msg</button>
    </div>
    <Father />
</template>