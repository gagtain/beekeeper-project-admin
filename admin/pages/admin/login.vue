<template>
<body>
  <div class="login">
    <div class="login-screen">
      <div class="app-title">
        <h1>Login</h1>
        <p v-if="error" class="form-error">Данного пользователя несуществует</p>
      </div>

      <div class="login-form">
        <div class="control-group">
        <input v-model="username" type="text" class="login-field" placeholder="username" id="login-name">
        <label class="login-field-icon fui-user" for="login-name"></label>
        </div>

        <div class="control-group">
        <input v-model="password" type="password" class="login-field" placeholder="password" id="login-pass">
        <label class="login-field-icon fui-lock" for="login-pass"></label>
        </div>

        <a @click="validation()" class="btn btn-primary btn-large btn-block">login</a>
        <a class="login-link" href="#">Lost your password?</a>
      </div>
    </div>
  </div>
</body>
</template>

<style scoped>
body {
font-family: Arial;
background-color: #f0f1f6;
}
.login {
width: 300px;
position: relative;
left: 33%;
top: 80px;
right: 0;
bottom: 0;
}
.login-screen {
background-color: #FFF;
padding: 20px;
border-radius: 5px
}

.app-title {
text-align: center;
color: hwb(0 0% 100%);
}

.login-form {
text-align: center;
}
.control-group {
margin-bottom: 10px;
}

input {
text-align: center;
background-color: #ECF0F1;
border: 2px solid transparent;
border-radius: 3px;
font-size: 16px;
font-weight: 200;
padding: 10px 0;
width: 250px;
transition: border .5s;
}

input:focus {
border: 2px solid #3498DB;
box-shadow: none;
}

.btn {
  border: 2px solid transparent;
  background: #3498DB;
  color: #ffffff;
  font-size: 16px;
  line-height: 25px;
  padding: 10px 0;
  text-decoration: none;
  text-shadow: none;
  border-radius: 3px;
  box-shadow: none;
  transition: 0.25s;
  display: block;
  width: 250px;
  margin: 0 auto;
}

.btn:hover {
  background-color: #2980B9;
  cursor: pointer;
}

.login-link {
  font-size: 12px;
  color: hsl(0, 0%, 0%);
  display: block;
  margin-top: 12px;
}
.form-error {
  color: red;
}
</style>

<script>
export default {
    data (){
    return {
        username: null,
        password: null,
        user: {
            username: 's',
            password: 1,
        },
        error: false,
        }
    },
    methods: {
        validation() {
            if (this.username == this.user.username && this.password == this.user.password) {
              this.$router.push({ path: '/admin'})
            } else {
              this.error = true
            }
        }
    }
}
</script>

