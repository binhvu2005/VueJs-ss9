<template>
    <div>
        <h1>them moi san pham</h1>
      <form @submit.prevent="addProduct">
        <div>
          <label for="productId">Mã sản phẩm:</label>
          <input id="productId" v-model="product.productId" type="text" required />
        </div>
        
        <div>
          <label for="productName">Tên sản phẩm:</label>
          <input id="productName" v-model="product.productName" type="text" required />
        </div>
  
        <div>
          <label for="price">Giá:</label>
          <input id="price" v-model="product.price" type="number" required />
        </div>
  
        <div>
          <label for="quantity">Số lượng:</label>
          <input id="quantity" v-model="product.quantity" type="number" required />
        </div>
  
        <button type="submit">Thêm mới</button>
      </form>
    </div>
  </template>
  
  <script setup>
import { reactive } from 'vue';
const product = reactive({
          productId: '',
          productName: '',
          price: 0,
          quantity: 0
        }) 
     function addProduct() {
        console.log('Product added:',product);
        product.productId = '';
        product.productName = '';
        product.price = 0;
        product.quantity = 0;

      }
    
  </script>
  
  <style scoped>
  

  </style>
  