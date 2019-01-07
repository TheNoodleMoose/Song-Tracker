<template>
  <div>
    <h1>Register</h1>
    <input type="text" name="username" v-model="userName" placeholder="Username">
    <br>
    <input type="email" name="email" v-model="email" placeholder="email">
    <br>
    <input type="text" name="password" v-model="password" placeholder="password">
    <br>
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from "@/services/AuthenticationService";
export default {
  data() {
    return {
      userName: "",
      email: "",
      password: ""
    };
  },
  methods: {
    async register() {
      const response = await AuthenticationService.register({
        userName: this.userName,
        email: this.email,
        password: this.password
      });
      console.log(response.data);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
