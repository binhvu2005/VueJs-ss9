<template>
    <div>
        <h1>them moi nguoi dung</h1>
      <form @submit.prevent="addUser">
        <div>
          <label for="productId">ho va ten:</label>
          <input id="productId" v-model="user.name" type="text" required />
        </div>
        
        <div>
          <label for="productName">email:</label>
          <input id="productName" v-model="user.email" type="text" required />
        </div>
  
        <div>
          <label for="price">pass:</label>
          <input id="price" v-model="user.pass" type="password" required />
        </div>
  
        <div>
          <label for="quantity">rePass:</label>
          <input id="quantity" v-model="user.rePass" type="password" required />
        </div>
  
        <button type="submit">dang ki</button>
      </form>
    </div>
  </template>
  
  <script setup>
import { reactive } from 'vue';
const user = reactive({
          name: '',
          email: '',
          pass: '',
          rePass: ''
        }) 
     function addUser() {
        console.log('Product added:',user);
        user.name = '';
        user.email = '';
        user.pass = '';
        user.rePass = '';
      }
    
  </script>
  
  <style scoped>
  

  </style>
  