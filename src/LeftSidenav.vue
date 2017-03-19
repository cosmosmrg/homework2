<template lang="html">
  <div class="left-sidenav">
    <el-menu theme="dark" class="el-menu-demo" mode="horizontal">
      <el-submenu index="2">
        <template slot="title"><i class="el-icon-menu"></i>Homework 2</template>
        <router-link :to="{ name: 'Posts.index' }">
          <el-menu-item index="2-1" router>Posts</el-menu-item>
        </router-link>
        <router-link :to="{ name: 'Posts.new' }">
          <el-menu-item index="2-2">New Posts</el-menu-item>
        </router-link>
        <el-menu-item index="2-3" @click.native="logout">Logout</el-menu-item>
      </el-submenu>
    </el-menu>
  </div>
</template>

<script>
import UsersApi from './api/users.js'

export default {
  methods: {
    toggleLeftSidenav () {
      this.$refs.leftSidenav.toggle()
    },
    logout () {
      UsersApi.logout()
    }
  }
}
</script>

<style lang="css">
</style>
