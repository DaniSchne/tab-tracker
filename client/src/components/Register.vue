<template>
  <div class="hello">
    <h1>Register</h1>

    <input type="email" name="Email" v-model="email" placeholder="Email" />
    <br>
    <input type="password" name="Password" v-model="password" placeholder="Password" />
    <br>
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
