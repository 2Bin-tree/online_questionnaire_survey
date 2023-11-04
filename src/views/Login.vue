<template>
  <div class="content">
    <div id="header">
      <h1>AirManageSystem</h1>
    </div>
    <div id="header1">
      <h1>_Mantou</h1>
    </div>
    <div id="login">
      <el-form ref="form" :model="form" label-width="20%">
        <el-form-item id="input1" label="USER">
          <el-input onfocus="if (value ==='请输入用户名'){value =''}"
                    onblur="if (value ===''){value='请输入用户名'}" v-model="form.username"></el-input>
        </el-form-item>
        <el-form-item id="input2" label="PassW:">
          <el-input onfocus="if (value ==='请输入密码'){value =''}"
                    onblur="if (value ===''){value='请输入密码'}" v-model="form.password"
                    text="password"></el-input>
        </el-form-item>
      </el-form>
      <el-row>
        <el-button plain @click="login" class="btn">Login</el-button>
        <el-button plain @click="register" class="reg">Register</el-button>
      </el-row>
    </div>
  </div>
</template>
<script>

export default {
  data() {
    return {
      form: {
        username: '请输入用户名',
        password: '请输入密码'
      }
    }
  },
  methods: {
    login() {
      if (this.form.username === '') {
        this.$message.error('用户名不能为空');
      } else if (this.form.password === '') {
        this.$message.error('密码不能为空');
      } else {
        this.axios.get('/login', {
          params: {
            name: this.form.username,
            password: this.form.password
          }
        }).then(res => {
          if (res.data.status === 200) {
            this.$router.push({
              path: '/home',
              query: {
                name: this.form.username
              }
            })
          } else {
            this.$alert('用户名或密码错误', '登录失败', {
              confirmButtonText: '确定',
              callback: action => {
                this.form.username = '',
                    this.form.password = ''
              }
            });
          }
        }).catch(err => {
          console.log("登录失败" + err);
        })
      }
    },
    register() {
      this.$router.push('/register')
    }
  }
}

</script>

<style scoped>
.content {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-image: linear-gradient(#f7fffc,#ffffff);
  background-size: 100% 100%;
}

#header {
  width: 450px;
//background: #ffffff; margin-right: auto;
  margin-left: auto;
  margin-top: 250px;
  font-size: 28px;
}

#header1 {
  width: 45px;
//background: red; margin-left: 800px;
//margin-right: 100px; margin-top: 20px;
  font-size: 14px;
}


#login {
  border-radius: 15px;
  height: 250px;
  width: 450px;
  box-shadow: 0 2px 12px 0 rgba(0, 0, 0, 0.25);
  background: #ffffff;
  opacity: 0.85;
  position: relative;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  margin-left: auto;
  margin-right: auto;
  margin-top: 20px;
  display: flex;
  text-align: center;
  flex-direction: column;
}

#login el-form {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  margin-top: 30px;
  flex-direction: column;
}

#input1 {
  margin-top: 40px;
  width: 380px;
  margin-left: auto;
  margin-right: auto;
}

#input2 {
  width: 380px;
  margin-left: auto;
  margin-right: auto;
}

.btn {
  width: 30%;
  margin: auto;
}

.reg {
  width: 30%;
  margin-top: auto;
  margin-left: 30px;
}
</style>