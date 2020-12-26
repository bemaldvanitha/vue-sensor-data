<template>

  <form @submit.prevent="handleSubmit">
    <input type="email" required placeholder="email" v-model="email"/>
    <input type="password" required placeholder="password" v-model="password"/>
    <button>Log In</button>
  </form>

</template>

<script>

export default {
  name: "LoginForm",
  data(){
    return {
      email: '',
      password: '',
    }
  },
  methods: {
    handleSubmit(){
      console.log(this.email);
      console.log(this.password);
    }
  },
}
</script>

<style scoped>

</style>