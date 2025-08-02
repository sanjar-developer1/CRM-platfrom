<template>
  <div class="login-wrapper">
    <form action="">
      <p>UserName</p>
      <input type="text" required v-model="usernameInp" />
      <p>Password</p>
      <input type="password" required v-model="passwordInp" />
      <button @click.prevent="login">Submit</button>
    </form>
  </div>
</template>

<script>
import { toast } from "vue3-toastify";

import "vue3-toastify/dist/index.css";

export default {
  data() {
    return {
      usernameInp: "",
      passwordInp: "",
    };
  },
  methods: {
    login() {
      if (this.usernameInp && this.passwordInp) {
        toast.success(`So'rov yuborildi`, {
          position: "top-center",
          timeout: 3000,
          closeOnClick: true,
          limit: 1,
        });
      } else {
        toast.error(`Iltimos ma'lumotlarni to'ldiring`, {
          position: "top-center",
          timeout: 3000,
          closeOnClick: true,
          limit: 1,
        });
      }
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.login-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  height: 100vh;
  background-color: rgb(67, 67, 67);
}
form {
  width: 300px;
  height: 400px;
  padding: 20px;
  background-color: #f9f9f9;
  border-radius: 8px;
  font-family: sans-serif;
  display: flex;
  flex-direction: column;
  align-items: left;
  justify-content: center;
  gap: 10px;
}

form input {
  width: 100%;
  padding: 8px;
  font-size: 14px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-sizing: border-box;
}

form button {
  margin-top: 15px;
  width: 100%;
  padding: 10px;
  background-color: rgb(51, 50, 50);
  border: none;
  color: white;
  font-size: 14px;
  border-radius: 5px;
  cursor: pointer;
}
</style>
