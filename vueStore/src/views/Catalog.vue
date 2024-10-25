<template>
    <div class="catalog">
      <div class="catalog-container">
        <ProductItem 
          v-for="product in products" 
          :key="product.id" 
          :product="product" 
          @add-to-cart="addToCart"
        />
      </div>
    </div>
  </template>
  
  <script>
  import ProductItem from '@/components/ProductItem.vue';
  import blockCilindrImg from '../assets/products-image/block_cilindr.jpg';
  import diskImg from '../assets/products-image/disk.jpg';
  import grmImg from '../assets/products-image/GRM.jpg';
  import bakImg from '../assets/products-image/bak.jpg';
  
  export default {
    components: {
      ProductItem
    },
    data() {
      return {
        products: [
          { id: 1, name: 'Бак цилиндров ВАЗ', price: 48090, image: blockCilindrImg },
          { id: 2, name: 'Тормозной диск АвтоВАЗ', price: 2990, image: diskImg },
          { id: 3, name: 'Комплект ГРМ LADA', price: 6690, image: grmImg },
          { id: 4, name: 'Бензобак ДСК', price: 5990, image: bakImg }
        ]
      };
    },
    methods: {
    saveProductsToLocalStorage() {
        localStorage.setItem('products', JSON.stringify(this.products));
    },
    addToCart(product) {
        let cart = JSON.parse(localStorage.getItem('cart')) || [];
        cart.push(product);
        localStorage.setItem('cart', JSON.stringify(cart));
        console.log('Товар добавлен в корзину', product);
    }
    },
    mounted() {
        this.saveProductsToLocalStorage(); // Сохраняем продукты в локальное хранилище
}
  }
  </script>
  
  <style scoped>
  .catalog {
    padding: 20px;
  }
  
  .catalog-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  </style>
  