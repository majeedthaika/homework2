<template>
  <div id="app">
    <div v-if="showLogoutButton()" class="sign-out" style="float: right;">
      <router-link :to="{ name: 'Posts.index' }">
        <el-button>All Posts</el-button>
      </router-link>
      <router-link :to="{ name: 'Posts.new' }">
        <el-button>New Post</el-button>
      </router-link>
      <el-button type="primary" @click.native="logout">Logout</el-button>
    </div>
    <br><br><br>
    <router-view></router-view>
  </div>
</template>

<script>
import UsersApi from './api/users.js'
import router from './router'
import store from './store.js'

export default {
  name: 'sign-out',
  methods: {
    logout () {
      console.log('methods.logout')
      UsersApi.logout(function (_response) {
        router.push({ name: 'Users.sign_in' })
      })
    },
    showLogoutButton () {
      return store.getters.loggedIn
    }
  }
}
</script>

<style>
</style>
