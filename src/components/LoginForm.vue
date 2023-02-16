<script>
  export default {
    data() {
      return {
        email: "",
        password: "",
      };
    },
    computed: {
      loginHandler() {
        const { email, password } = this;
        let message = `Login success with email ${email}`;
        const regex = /^\S+@\S+\.\S+$/;

        if (!email) message = "Email is required";
        else if (!email.toLowerCase().match(regex))
          message = "Invalid Email format";
        else if (!password) message = "Password is required";
        else if (password.length < 8) message = "Password min is 8 characters";

        console.log(message);
      },
    },
  };
</script>

<template>
  <form method="post" @submit.prevent="loginHandler">
    <label>Email address</label>
    <input
      v-model="email"
      placeholder="Enter Email Address"
      type="text"
      name="email"
    />
    <label>Password</label>
    <input
      v-model="password"
      placeholder="Enter Password"
      type="password"
      name="password"
    />
    <input type="submit" value="Login" />
  </form>
</template>

<style scoped>
  form {
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
    margin-bottom: 2rem;
  }

  form label {
    font-size: 1rem;
  }

  input {
    border-radius: 0.5em;
    border: 0;
    padding: 0.5rem 0.5rem;
    font-size: 1rem;
  }

  input:focus {
    outline: none;
  }

  input[type="submit"] {
    font-size: 1rem;
    font-weight: bold;
  }

  input[type="submit"]:hover {
    background-color: rgb(45, 45, 45);
    color: white;
  }
</style>
