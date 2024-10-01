<template>
    <div>
      <h1>Đăng ký tài khoản</h1>
      <form @submit.prevent="addUser">
        <div>
          <label for="studentName">Tên sinh viên:</label>
          <input id="studentName" v-model="user.name" type="text"  required />
        </div>
  
        <div>
          <label for="email">Email:</label>
          <input id="email" v-model="user.email" type="email" required />
        </div>
  
        <div>
          <label for="password">Mật khẩu:</label>
          <input id="password" v-model="user.password" type="password" required />
        </div>
  
        <div>
          <label for="address">Địa chỉ:</label>
          <input id="address" v-model="user.address" type="text" />
        </div>
  
        <button type="submit">Đăng ký</button>
      </form>
  
      <p v-if="successMessage" style="color: green">{{ successMessage }}</p>
      <p v-if="errorMessage" style="color: red">{{ errorMessage }}</p>
    </div>
  </template>
  
  <script setup>
  import { reactive, ref } from 'vue';
  
  const user = reactive({
    name: '',
    email: '',
    password: '',
    address: ''
  });
  
  const successMessage = ref('');
  const errorMessage = ref('');
  
  const studentNameInput = ref(null);
  
  function addUser() {
    if (!user.name || !user.email || !user.password) {
      errorMessage.value = 'Vui lòng điền đầy đủ thông tin!';
      successMessage.value = '';
      return;
    }
  
    const storedUsers = JSON.parse(localStorage.getItem('users')) || [];
    const emailExists = storedUsers.some(storedUser => storedUser.email === user.email);
    if (emailExists) {
      errorMessage.value = 'Email đã tồn tại!';
      successMessage.value = '';
      return;
    }
  
    storedUsers.push({ ...user });
    localStorage.setItem('users', JSON.stringify(storedUsers));
  
    successMessage.value = 'Đăng ký tài khoản thành công!';
    errorMessage.value = '';
  
    user.name = '';
    user.email = '';
    user.password = '';
    user.address = '';
  

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
  