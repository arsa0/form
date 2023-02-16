<script>
  export default {
    data() {
      return {
        firstName: "",
        lastName: "",
        email: "",
        password: "",
        tna: false,
      };
    },
    computed: {
      registerHandler() {
        const { firstName, lastName, email, password, tna } = this;

        let message = `Register success with email ${email}`;
        const regex = /^\S+@\S+\.\S+$/;

        if (!firstName) message = "First Name is required";
        else if (!lastName) message = "Last Name is required";
        else if (!email) message = "Email is required";
        else if (!email.toLowerCase().match(regex))
          message = "Invalid Email format";
        else if (!password) message = "Password is required";
        else if (password.length < 8) message = "Password min is 8 characters";
        else if (!tna)
          message =
            "You need to agree to our Terms and Condition before register";

        console.log(message);
      },
    },
  };
</script>

<template>
  <form method="post" @submit.prevent="registerHandler">
    <label>First Name</label>
    <input
      placeholder="Enter First Name"
      v-model="firstName"
      type="text"
      name="firstName"
    />
    <label>Last Name</label>
    <input
      placeholder="Enter Last Name"
      v-model="lastName"
      type="text"
      name="lastName"
    />
    <label>Email address</label>
    <input placeholder="Enter Email" v-model="email" type="text" name="email" />
    <label>Password</label>
    <input
      placeholder="Enter Password"
      v-model="password"
      type="password"
      name="password"
    />
    <div class="row">
      <input v-model="tna" type="checkbox" name="aggreement" id="tna" />
      <label for="tna"
        >To register with us please tick to agree with our
        <a href="#terms">Terms and Agreement</a></label
      >
    </div>
    <input type="submit" value="Register" />
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

  input[type="checkbox"] {
    width: auto;
    margin-right: 0.5rem;
  }

  label a {
    text-decoration: none;
    color: var(--vt-c-black);
    font-weight: bold;
  }
</style>
