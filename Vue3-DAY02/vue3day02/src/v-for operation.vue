<script>
//import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      id:4,
      List: [
        {
          id: 1,
          name: '张三',
          age: 18
        },
        {
          id: 2,
          name: '李四',
          age: 20
        },
        {
          id: 3,
          name: '王五',
          age: 22
        },
        {
          id: 4,
          name: '赵六',
          age: 24
        },
      ]
    }
  },
  methods: {
    insertList() {
      this.id += 2;
      this.List.splice(1, 0, { id: this.id+1, name: '小明', age: 16 }, { id: this.id+2, name: '小红', age: 17 });
    },
    reverseList() {
      this.List.reverse();
    }
  }
}
</script>

<template>
  <div>
    <ul>
      <li v-for="(item, index) in List" :key="item.id">
        <span>{{ item.id }}</span>
        <span>{{ item.name }}</span>
        <span>{{ item.age }}</span>
      </li>
    </ul>
  </div>
  <button @click="reverseList">反转</button>
  <button @click="insertList">插入</button>
</template>

<style scoped></style>
