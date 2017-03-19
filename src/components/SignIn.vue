<template>
  <div class="sign-in">
    <el-card class="box-card">
      <el-form label-width="120px">
        <el-form-item label="Email">
          <el-input v-model="email" placeholder=""></el-input>
        </el-form-item>
        <el-form-item label="Password">
          <el-input v-model="password" placeholder="" type="password" @keyup.enter.native="login"></el-input>
        </el-form-item>
        <el-button style="margin-left:40%"type="primary" @click.native="login">Login</el-button>
      </el-form>
    </el-card>
  </div>
</template>

<script>
import UsersApi from '../api/users.js'
import router from '../router'

export default {
  name: 'sign-in',
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    login () {
      console.log('methods.login')
      UsersApi.login(this.email, this.password, function (_response) {
        // NOTE: Posts.index is not yet implemented
        router.push({ name: 'Posts.index' })
      })
    }
  }
}
</script>

<style>
  .text {
    font-size: 14px;
  }

  .item {
    padding: 18px 0;
  }

  .clearfix:before,
  .clearfix:after {
      display: table;
      content: "";
  }
  .clearfix:after {
      clear: both
  }

  .box-card {
    width: 480px;
    margin-left: 27%;
    margin-top: 10%;
  }
</style>
