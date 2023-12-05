<script>
import Son from './Son.vue'
export default {
    data() {
        return {
            fatherMsg:"this is Father" 
        }
    },
    methods:{

    },
    components:{
        Son
    },
}
</script>

<template>
      <Son />
</template>