<template>
  <div id="app">
    <nav>
      <router-link to="/">Каталог</router-link>
      <router-link to="/cart">Корзина</router-link>
    </nav>
    <router-view />
  </div>
</template>

<script>
export default {
  name: 'App',
}
</script>

<style>

nav {
  background-color: #040404;
  padding: 10px;
}

nav a {
  color: white;
  margin-right: 15px;
  text-decoration: none;
  font-size: 18px;
}

nav a:hover {
  text-decoration: underline;
}

body {
  background-color: #f7f7f7;
  font-family: Arial, sans-serif;
}

</style>
