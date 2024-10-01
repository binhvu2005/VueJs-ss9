<template>
    <form action="">
      <input type="range"  v-model="val">
      <p>tien do hoan thanh:{{val}}%</p>
    </form>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  const val = ref(50);
  </script>
  
  <style>
  
  </style>