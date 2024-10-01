<template>
    <form action="">
      <input type="checkbox" name="gt" v-model="val" value="gai c1">gai c1 <br>
      <input type="checkbox" name="gt" v-model="val" value="gai c2">gai c2 <br>
      <input type="checkbox" name="gt" v-model="val" value="gai c3">gai c3 <br>
      <input type="checkbox" name="gt" v-model="val" value="gai dh">gai dh <br>
      <input type="checkbox" name="gt" v-model="val" value="gai 1 con">gai 1 con <br>

      <p>so thich:{{val}}</p>
    </form>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  const val = ref([]);
  </script>
  
  <style>
  
  </style>