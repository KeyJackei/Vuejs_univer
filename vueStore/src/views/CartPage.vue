<template>
    <div class="cart-container">
      <Cart /> <!-- Используем компонент Cart для отображения содержимого корзины -->
    </div>
  </template>
  
  <script>
  import Cart from '@/components/Cart.vue';
  
  export default {
    components: {
      Cart
    }
  };
  </script>
  
  <style scoped>
  .cart-container {
    padding: 20px;
  }
  </style>
  