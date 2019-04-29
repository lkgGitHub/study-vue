<template>
  <div>
      <form v-if="!is_register">
        <p>用户名</p>
        <input type="text" v-model="username">
        <p>密码</p>
        <input type="password" v-model="password">
        <p></p>
        <button type="button" @click="login()">登录</button>
        <button type="button" @click="registerClick()">注册</button>
      </form>

      <form v-if="is_register">
        <p>用户名</p>
        <input type="text" v-model="username">
        <p>密码</p>
        <input type="password" v-model="password">
        <p>确认密码</p>
        <input type="password" v-model="password2">
        <p></p>
        <button type="button" @click="addUser()">确认</button>
        <button type="button" @click="cancel()">取消</button>
      </form>
  </div>
</template>

<script>
export default {
  name: 'login',
  data(){
    return {
      is_register: false,
      username: '',
      password: '',
      password2: ''
    }
  },
  methods: {
    login(){
      if(this.username === localStorage.getItem('username')&& this.password ===localStorage.getItem('password')){
        this.username = ''
        this.password = ''
        this.$router.push('/home/list')
      }else{
        alert("登录失败")
      }
    },
    registerClick(){
        this.is_register = true
        this.username = ''
        this.password = ''
        this.password2 = ''
    },

    addUser(){
       if(this.password === this.password2){
        localStorage.setItem("username", this.username)
        localStorage.setItem("password", this.password)
        this.username = ''
        this.password = ''
        this.password2 = ''
        this.is_register = false
      }else{
        alert("两次输入密码不想通")
      }
    },
    cancel(){
      this.username = ''
      this.password = ''
      this.password2 = ''
      this.is_register = false
    }
  }
}
</script>

<style scoped>

</style>

