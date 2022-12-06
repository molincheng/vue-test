<template>
  <div class="hello">
    <ul>
      <li v-for="(item,index) in list" :key="index" >{{item.name}} -- {{item.age}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'studentApp',
  data(){
    return{
      list:[]
    }
  },
  mounted(){
    this.$bus.$on('fun1',obj=>{
      this.list.push(obj)
      console.log(obj)
    })
  },
  beforeDestroy(){
    console.log('student组件销毁了')
    this.$bus.$off('fun1')
  }
}
</script>

<style>
.hello{
  margin-top:20px;
  width:350px;
  background:pink;
}
</style>