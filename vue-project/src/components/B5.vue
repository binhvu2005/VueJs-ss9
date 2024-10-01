<template>
    <form action="">
      <input type="radio" name="gt" v-model="val" value="nam">nam <br>
      <input type="radio" name="gt" v-model="val" value="nu">nu <br>
      <input type="radio" name="gt" v-model="val" value="gay">gay <br>
      <p>gioi tinh:{{val}}</p>
    </form>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  const val = ref('');
  </script>
  
  <style>
  
  </style>