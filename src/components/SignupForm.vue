<template>

  <form @submit.prevent="handleSubmit">
    <input type="text" required placeholder="display name" v-model="name"/>
    <input type="email" required placeholder="email" v-model="email"/>
    <input type="password" required placeholder="password" v-model="password"/>
    <button>Sign up</button>
  </form>

</template>

<script>
  import axios from "axios";
  export default {
    name: "SignupForm",
    data(){
      return {
        name: '',
        email: '',
        password: '',
        error: ''
      }
    },
    methods: {
      handleSubmit(){
        axios.post('http://localhost:5000/signup',{
          'name': this.name,
          'email': this.email,
          'password': this.password,
        }).then(res => {

          this.$router.push('/charts');

        }).catch(err => {

          console.log(err);

        })
      }
    },
  }
</script>

<style scoped>

</style>