<template>
    <form action="">
     
      <input type="date"  v-model="val">
      <p>ngay sinh:{{val}}</p>
    </form>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  const val = ref('');
  </script>
  
  <style>
  
  </style>