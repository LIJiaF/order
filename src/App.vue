<template>
  <div id="app">
    <admin-login></admin-login>
  </div>
</template>

<script>
import Login from "./components/login/Login.vue"
export default {
  name: 'App',
  components: {
    "admin-login":Login
  }
}
</script>

<style>
</style>
