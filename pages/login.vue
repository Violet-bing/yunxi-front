<template>
  <div class="main">
    <div class="title">
      <a class="active" href="/login">登录</a>
      <span>·</span>
      <a href="/register">注册</a>
    </div>
    <div class="sign-up-container">
      <el-form ref="userForm" :model="user">
        <el-form-item :rules="[{required: true, message: '请输入手机号码', trigger: 'blur' },{validator:checkPhone, trigger: 'blur'}]" class="input-prepend restyle" prop="mobile" >
          <div >
            <el-input v-model="user.mobile" type="text" placeholder="手机号" />
            <i class="iconfont icon-phone" />
          </div>
        </el-form-item>
        <el-form-item :rules="[{ required:true, message: '请输入密码', trigger: 'blur' }]" class="input-prepend" prop="password" >
          <div>
            <el-input v-model="user.password" type="password" placeholder="密码" />
            <i class="iconfont icon-password"/>
          </div>
        </el-form-item>
        <div class="btn">
          <input type="button" class="sign-in-button" value="登录" @click="submitLogin">
        </div>
      </el-form>

    </div>
  </div>
</template>
<script>
import '~/assets/css/sign.css'
import '~/assets/css/iconfont.css'
import cookie from 'js-cookie'


export default {
  layout: 'sign',
  data() {
    return {
      user: {
        mobile: '',
        password: ''
      },
      loginInfo: {}
    }
  },
  methods: {

  }
}
</script>
<style>
  .el-form-item__error{
    z-index: 9999999;
  }
</style>
