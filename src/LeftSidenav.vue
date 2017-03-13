<template lang="html">
  <div class="left-sidenav">
    <md-toolbar>
      <md-button class="md-icon-button" @click.native="toggleLeftSidenav">
        <md-icon>menu</md-icon>
      </md-button>
      <h2 class="md-title">Homework 2</h2>
    </md-toolbar>
    <md-sidenav class="md-left" ref="leftSidenav">
      <md-toolbar class="md-large">
        <div class="md-toolbar-container">
          <h3 class="md-title">Sidenav content</h3>
        </div>
      </md-toolbar>
      <md-list>
        <router-link :to="{ name: 'Posts.index' }">
          <md-list-item class="md-raised md-primary" >Posts</md-list-item>
        </router-link>
        <router-link :to="{ name: 'Posts.new' }">
          <md-list-item class="md-raised md-primary" >New Posts</md-list-item>
        </router-link>
        <md-list-item class="md-raised md-primary" @click.native="logout">Logout</md-list-item>
      </md-list>
    </md-sidenav>

  </div>
</template>

<script>
import UsersApi from './api/users.js'
import router from './router'

export default {
  methods: {
    toggleLeftSidenav () {
      this.$refs.leftSidenav.toggle()
    },
    logout () {
      console.log('methods.logout')
      UsersApi.logout(function (_response) {
        // NOTE: Posts.index is not yet implemented
        router.push({ name: 'Users.sign_in' })
      })
    }
  }
}
</script>

<style lang="css">
</style>
