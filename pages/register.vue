<template>
  <div class="main">
    <div class="title">
      <a href="/login">登录</a>
      <span>·</span>
      <a class="active" href="/register">注册</a>
    </div>
    <div class="sign-up-container">
      <el-form ref="userForm" :model="params">
        <el-form-item :rules="[{required: true, message: '请输入你的昵称', trigger: 'blur' }]" class="input-prepend restyle" prop="nickname" >
          <div>
            <el-input v-model="params.nickname" type="text" placeholder="你的昵称" />
            <i class="iconfont icon-user"/>
          </div>
        </el-form-item>
        <el-form-item :rules="[{ required: true, message: '请输入手机号码', trigger: 'blur' },{validator:checkPhone, trigger: 'blur'}]" class="input-prepend restyle no-radius" prop="mobile" >
          <div>
            <el-input v-model="params.mobile" type="text" placeholder="手机号" />
            <i class="iconfont icon-phone"/>
          </div>
        </el-form-item>

        <el-form-item :rules="[{ required:true, message: '请输入密码', trigger: 'blur' }]" class="input-prepend" prop="password" >
          <div>
            <el-input v-model="params.password" type="password" placeholder="设置密码" />
            <i class="iconfont icon-password"/>
          </div>
        </el-form-item>
        <div class="btn">
          <input type="button" class="sign-up-button" value="注册" @click="submitRegister()">
        </div>
        <p class="sign-up-msg">
          点击 “注册” 即表示您同意并愿意遵守简书
          <br>
          <a target="_blank" href="http://www.jianshu.com/p/c44d171298ce">用户协议</a>
          和
          <a target="_blank" href="http://www.jianshu.com/p/2ov8x3">隐私政策</a> 。
        </p>
      </el-form>
    </div>
  </div>
</template>
<script>
import '~/assets/css/sign.css'
import '~/assets/css/iconfont.css'


export default {
  layout: 'sign',
  data() {
    return {
      params: {
        mobile: '',
        code: '',
        nickname: '',
        password: ''
      },
      sending: true, // 是否发送验证码
      second: 60, // 倒计时间
      codeTest: '获取验证码'
    }
  },
  methods: {

  }
}
</script>
