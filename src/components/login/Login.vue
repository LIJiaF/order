<template>
  <div class="login-wrapper">
    <h3 class="title">点餐后台管理系统</h3>
    <form action="localhost/phpsendbox/admin-login.php" method="post" class="animated zoomIn">
      <h4 class="text-center" v-if="!flag">登录</h4>
      <h4 class="text-center"v-else>注册</h4>
      <div class="form-group">
        <label for="">邮箱：</label>
        <input type="email" class="form-control" name="email">
      </div>
      <div class="form-group">
        <label for="">密码：</label>
        <input type="password" class="form-control" name="password">
      </div>
      <div class="form-group comfirePassword" v-if="flag">
        <label for="">确认密码：</label>
        <input type="password" class="form-control">
      </div>
      <div class="from-group" v-if="!flag">
        <input type="radio">
        <label for="">记住密码</label>
      </div>
      <button class="btn btn-success btn-block" v-if="!flag" type="submit" name="submit">登录</button>
      <button class="btn btn-success  btn-block" v-else>立即注册</button>
      <p v-if="!flag">
        <span class="tip">还没有账号？</span><a href="#" class="register-tip" @click="toRegister">马上注册</a>
      </p>
      <p v-else>
        <span class="tip">已有账号？</span><a href="#" class="register-tip" @click="toRegister">马上登录</a>
      </p>

    </form>
  </div>
</template>
<script>
export default {
  name: 'login',
  data() {
    return {
      flag:false,
    }
  },
  methods:{
    toRegister(){
      this.flag = !this.flag;
    },
  }
}

</script>
<style scoped>
.login-wrapper{
  width:100%;
  height: 100%;
  position:absolute;
  background-image:url("../../assets/login_bg.jpg");
  background-repeat: no-repeat;
  background-size: cover;
}
form {
  background: #fff;
  width: 320px;
  position: absolute;
  left: 50%;
  top: 50%;
  margin-left: 240px;
  margin-top: -250px;
  padding:20px;
}

.btn {
  margin-top: 25px;
}
form .form-group:first-child {
  padding-bottom: 20px;
}

.title {
  padding-top: 30px;
  padding-left: 30px;
  color: #fff;
}

form .tip,
.register-tip {
  font-size: 12px;
}

form .comfirePassword {
  display: none;
}

</style>
