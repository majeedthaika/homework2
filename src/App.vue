<template>
  <div id="app">
    <div class="sign-out" style="float: right;">
      <el-button  v-if="showLogoutButton()" type="primary" @click.native="logout">Logout</el-button>
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
      return store.state.auth
    }
  }
}
</script>

<style>
</style>
