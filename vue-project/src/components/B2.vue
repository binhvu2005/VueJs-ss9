<template>
  <div>
    <label for="colorPicker">Chọn màu:</label>
    <input id="colorPicker" type="color" v-model="selectedColor" />
    <p>
      Mã màu đã chọn: <strong>{{ selectedColor }}</strong>
    </p>
  </div>
</template>

<script setup>
import { ref } from "vue";
const selectedColor = ref("#000000");
</script>

<style scoped>
/* Thêm style nếu cần */
</style>
