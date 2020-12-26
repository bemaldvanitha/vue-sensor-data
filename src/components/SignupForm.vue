<template>

  <form @submit.prevent="handleSubmit">
    <input type="text" required placeholder="display name" v-model="name"/>
    <input type="email" required placeholder="email" v-model="email"/>
    <input type="password" required placeholder="password" v-model="password"/>
    <button>Sign up</button>
  </form>

</template>

<script>

export default {
  name: "SignupForm",
  data(){
    return {
      name: '',
      email: '',
      password: '',
    }
  },
  methods: {
    handleSubmit(){
      console.log(this.name);
      console.log(this.email);
      console.log(this.password);
    }
  },
}
</script>

<style scoped>

</style>