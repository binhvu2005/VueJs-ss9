<template>
    <div>
      <h1>Đăng nhập tài khoản</h1>
      <form @submit.prevent="loginUser">
        <div>
          <label for="email">Email:</label>
          <input id="email" v-model="login.email" type="email" required />
        </div>
  
        <div>
          <label for="password">Mật khẩu:</label>
          <input id="password" v-model="login.password" type="password" required />
        </div>
  
        <button type="submit">Đăng nhập</button>
      </form>
  
      <p v-if="successMessage" style="color: green">{{ successMessage }}</p>
      <p v-if="errorMessage" style="color: red">{{ errorMessage }}</p>
    </div>
  </template>
  
  <script setup>
  import { reactive, ref } from 'vue';
  
  const login = reactive({
    email: '',
    password: ''
  });
  
  const successMessage = ref('');
  const errorMessage = ref('');
  
  function loginUser() {
    if (!login.email || !login.password) {
      errorMessage.value = 'Vui lòng điền đầy đủ thông tin!';
      successMessage.value = '';
      return;
    }
  
    const storedUsers = JSON.parse(localStorage.getItem('users')) || [];
  
    const userFound = storedUsers.find(
      storedUser => storedUser.email === login.email && storedUser.password === login.password
    );
  
    if (userFound) {
      successMessage.value = 'Đăng nhập thành công!';
      errorMessage.value = '';
    } else {
      errorMessage.value = 'Đăng nhập thất bại, email hoặc mật khẩu không đúng!';
      successMessage.value = '';
    }
  
    login.email = '';
    login.password = '';
  }
  </script>
  
  <style scoped>
  form {
    margin-bottom: 20px;
  }
  
  input {
    margin-bottom: 10px;
    display: block;
  }
  </style>
  