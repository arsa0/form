<script>
  import RegisterForm from "../components/RegisterForm.vue";
  import { RouterLink } from "vue-router";

  export default {
    components: {
      RegisterForm,
    },
    data() {},
  };
</script>

<template>
  <section>
    <h2>Create Your Account</h2>
    <RegisterForm />
    <div class="center">
      Already have an account? <RouterLink to="/login">Sign In</RouterLink>
    </div>
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
