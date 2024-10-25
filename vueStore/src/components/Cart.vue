<template>
  <div>
    <h1>Корзина</h1>
    <ul>
      <li v-for="(item, index) in cart" :key="index">
        {{ item.name }} - {{ item.price }} ₽
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cart: JSON.parse(localStorage.getItem('cart')) || []
    };
  }
}
</script>
