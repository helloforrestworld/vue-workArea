<template>
  <div class="main">
    <div class="home-header">
      <img src="../assets/forrest.png" alt="">
      <div class="portrait">
        <router-link v-if="!isLogin"  to="/login" tag="span">登录</router-link>
        <img v-if="isLogin" src="../assets/portrait.png" alt="">
      </div>

    </div>
    <div class="phrase">
      一起学习Vue-router
    </div>
    <div class="btns">
      <router-link to="/project" tag="div" class=" trans">我的项目</router-link>
      <router-link to="/doc" tag="div" class=" trans">我的文档</router-link>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'home',
    data(){
      return {
        isLogin:false
      }
    },
    created() {
      // 验证是否登录了
      this.isLogin = this.$local.fetch('login').login
    }
  }
</script>
<style>

</style>
