<template>
  <div id="app">
    <div class="app">
      <h2>app</h2>
      <button @click="send" >给学生发送一份信</button>
    </div>
    <studentApp v-if="isShow" ></studentApp>
    <button @click="isShow=!isShow">是否显示学生</button>
  </div>
</template>

<script>
import studentApp from './components/Student.vue'

export default {
  name: 'App',
  data(){
    return{
      isShow:true
    }
  },
  components: {
    studentApp
  },
  methods:{
    send(){
      this.$bus.$emit('fun1',{name:'lisi',age:22})
    }
  }
}
</script>

<style>
.app{
  width:350px;
  height:80px;
  background:red;
}
</style>