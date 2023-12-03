<script>
//import HelloWorld from './components/HelloWorld.vue'
export default {
  data() {
    return {
      //学生类（数组），名字，学号
      students: [
        { name: '张三', id: 1 },
        { name: '李四', id: 2 },
        { name: '王五', id: 3 },
        { name: '赵六', id: 4 },
      ],

    }
  },
  methods: {
    addStudent() {
      //头部添加
      this.students.unshift({ name: '小明', id: 5 });
    },
    watch: {


    }
  }
}
</script>

<template>
  <div>
    <table class="students">
      <thead>
        <tr>
          <tr>选择</tr>
          <th>姓名</th>
          <th>学号</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in students" :key="item.name">
          <!-- 添加复选框 -->
          <td><input type="checkbox"></td>
          <td>{{item.name}}</td>
          <td>{{item.id}}</td>
        </tr>
      </tbody>
    </table>
  </div>
  <button @click="addStudent">添加学生</button>
</template>

<style scoped>
.students {
  /* 表格实体线 */
  border-collapse: collapse;
  /* 表格外边框 */
  border: 2px solid #000;


}
</style>
