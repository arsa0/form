<script>
  import { RouterLink } from "vue-router";
  import LoginForm from "../components/LoginForm.vue";

  export default {
    components: {
      LoginForm,
    },
  };
</script>

<template>
  <section>
    <h2>Login to your Account</h2>
    <LoginForm />
    <p class="center">
      Don't have an account? <RouterLink to="/register">Register</RouterLink>
    </p>
    <p class="center">
      <a href="#forgot-password">Forgot your password?</a>
    </p>
  </section>
</template>

<style scoped>
  section {
    padding: 2em;
    background-color: rgb(215, 215, 215);
    border-radius: 0.5em;
    width: 35%;
  }

  section h2 {
    margin-bottom: 2rem;
    font-size: 2rem;
  }

  .center {
    text-align: center;
  }

  section a {
    text-decoration: none;
    font-weight: bold;
    color: var(--vt-c-black);
  }
</style>
