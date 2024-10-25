<template>
    <div class="product-details" v-if="product">
      <img :src="product.image" alt="Product image" class="product-image" />
      <h2>{{ product.name }}</h2>
      <p class="product-price">{{ product.price }} ₽</p>
      <button class="add-to-cart" @click="addToCart">В корзину</button>
    </div>
    <div v-else>
      <p>Товар не найден.</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        product: null
      };
    },
    mounted() {
      const productId = this.$route.params.id; // Получаем ID из маршрута
      const products = JSON.parse(localStorage.getItem('products')); // Получаем список продуктов из локального хранилища
      this.product = products ? products.find(p => p.id == productId) : null; // Ищем продукт по ID
    },
    methods: {
      addToCart() {
        if (this.product) {
          let cart = JSON.parse(localStorage.getItem('cart')) || [];
          cart.push(this.product);
          localStorage.setItem('cart', JSON.stringify(cart));
          console.log('Товар добавлен в корзину', this.product);
        }
      }
    }
  }
  </script>
  
  <style scoped>
  .product-details {
    text-align: center;
  }
  
  .product-image {
    max-width: 100%;
    height: auto;
  }
  </style>
  