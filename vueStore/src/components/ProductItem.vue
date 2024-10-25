<template>
    <div class="product-card">
      <img :src="product.image" alt="Product image" class="product-image" />
      <div class="product-details">
        <h3>{{ product.name }}</h3>
        <p class="product-price">{{ product.price }} ₽</p>
        <button class="add-to-cart" @click="addToCart">В корзину</button>
        <router-link :to="'/product/' + product.id" class="details-link">Подробнее</router-link>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      product: Object
    },
    methods: {
      addToCart() {
        this.$emit('add-to-cart', this.product);
      }
    }
  }
  </script>
  
  <style scoped>
  .product-card {
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 16px;
    margin: 16px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
    transition: transform 0.2s;
    background-color: #fff;
  }
  
  .product-card:hover {
    transform: translateY(-4px);
  }
  
  .product-image {
    max-width: 100%;
    height: auto;
    border-radius: 4px;
  }
  
  .product-details {
    margin-top: 12px;
    text-align: center;
  }
  
  .product-price {
    font-size: 18px;
    font-weight: bold;
    color: #333;
  }
  
  .add-to-cart {
    background-color: #28a745;
    color: white;
    border: none;
    padding: 10px 15px;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.2s;
  }
  
  .add-to-cart:hover {
    background-color: #218838;
  }
  
  .details-link {
    display: inline-block;
    margin-top: 8px;
    text-decoration: none;
    color: #007bff;
    transition: color 0.2s;
  }
  
  .details-link:hover {
    color: #0056b3;
  }
  </style>
  