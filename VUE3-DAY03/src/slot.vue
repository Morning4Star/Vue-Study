<script>
import Content from './components/Content.vue'
import Son from './components/Son.vue'
import GrandFather from './components/GrandFather.vue'
export default {
  data() {
    return {
      getContentmsg:"",
      msg:"我是App组件的msg",
    }
  },
  methods: {
    Sort(arr){
      // arr.sort(function f(a,b){return a-b})
      arr.sort((a,b) => a-b)
      return arr
    },
    getSonMsg(msg) {
      this.msg = msg
    }
  },
  components: {
    Content,
    Son,
    GrandFather
},
  mounted() {
    this.getContentmsg = this.$refs.getContent.contentMsg
  }
}
</script>

<template>
  <div>
    <Content ref="getContent">
      <template v-slot:a>
        <h1>插槽一</h1>
        <h1>{{msg}}</h1>
        <h1>{{getContentmsg}}</h1>
      </template>
      <template v-slot:b>
        <h1>插槽二</h1>
      </template>
      <template v-slot:c="props">
        <ul>
          <li v-for="item in Sort(props.list)" :key="item">
            {{ item }}
          </li>
        </ul>
        <!-- <ol>
          <li v-for="item in props.list" :key="item">
            {{ item }}
          </li>
        </ol> -->
      </template>
    </Content>
  </div>
  <div>
    <!-- <Son @sonMsg="getSonMsg">
      {{ msg }}
    </Son> -->
    <!-- <Son></Son> -->
    <GrandFather></GrandFather>
  </div>
</template>

<style scoped>

</style>
