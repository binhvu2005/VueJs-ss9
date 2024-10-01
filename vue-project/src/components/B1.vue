<template>
  <form action="">
    <label for="email">Email</label><br>
    <input type="text" name="email" v-model="val">
    <p>gia tri:{{val}}</p>
  </form>
</template>

<script setup>
import { ref } from 'vue';
const val = ref('');
</script>

<style>

</style>