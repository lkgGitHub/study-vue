<template>
<div>
  <p>标题</p>
  <input type="text" v-model="title">
   <p>内容</p>
  <input type="text" v-model="content">
  <button type="button" @click="add()">添加</button>
</div>  
</template>

<script>
import store from '@/store'
export default {
  name: 'Add',
  store,
  data(){
    return{
      title:'',
      content:''
    }
  },
  methods:{
    add(){
      store.commit('addItem', {title:this.title, comtent:this.content})
      this.title = ''
      this.content = ''
    }
  }
}
</script>

<style scoped>

</style>

