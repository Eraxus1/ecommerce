<template>
  <div id="app">
    <header>
      <div class="contact">
        <router-link to="/">Anasayfa</router-link>
        <router-link to="/about">Hakkımda</router-link>
      </div>
      <div class="shop">
        <button @click="showCart = !showCart">
          <i class="fa-solid fa-basket-shopping-simple">
            <span>{{ cart.length }}</span>
          </i>
        </button>
        <div class="cart-popup" v-if="showCart">
          <h2>Sepet</h2>
          <ul>
            <li v-for="(item, index) in cart">
              {{ item.name }}
            </li>
          </ul>
        </div>
      </div>

    </header>

    <div class="product-list">
      <div class="product" v-for="(product, index) in products" :key="index">
        <img :src="product.image" :alt="product.name">
        <p>{{ product.name }}</p>
        <button @click="addToCart(product)">Sepete Ekle</button>
      </div>
    </div>
    <div class="product-list">
      <div class="product" v-for="(product, index) in products2" :key="index">
        <img :src="product.image" :alt="product.name">
        <p>{{ product.name }}</p>
        <button @click="addToCart(product)">Sepete Ekle</button>
      </div>
    </div>


  </div>
</template>

<script>
export default {
  data() {
    return {
      showCart: false,
      products: [
        {
          name: "New short-sleeved printed shirt men and women casual beach clothes1",
          image: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Hcb02a9cd42164e6e9c00d88d56e14088u.jpg?v=1677236060&width=823",
        },
        {
          name: "New short-sleeved printed shirt men and women casual beach clothes1",
          image: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Scd79a079f9274c93aec8794ea070a1d5p.jpg?v=1677011330&width=823",
        },
        {
          name: "New short-sleeved printed shirt men and women casual beach clothes1",
          image: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Sa8041d0da32a40eba324b01da56fd59ad.jpg?v=1677010912&width=823",
        },
        {
          name: "New short-sleeved printed shirt men and women casual beach clothes1",
          image: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/S730d72a308414fb796aebe7e02a35a8ck.jpg?v=1677010854&width=823",
        }
      ],
      products2: [
        {
          name: " short-sleeved printed shirt men and women casual beach clothes1",
          image: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Hcb02a9cd42164e6e9c00d88d56e14088u.jpg?v=1677236060&width=823",
        },
        {
          name: " short-sleeved printed shirt men and women casual beach clothes1",
          image: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Scd79a079f9274c93aec8794ea070a1d5p.jpg?v=1677011330&width=823",
        },
        {
          name: " short-sleeved printed shirt men and women casual beach clothes1",
          image: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Sa8041d0da32a40eba324b01da56fd59ad.jpg?v=1677010912&width=823",
        },
        {
          name: " short-sleeved printed shirt men and women casual beach clothes1",
          image: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/S730d72a308414fb796aebe7e02a35a8ck.jpg?v=1677010854&width=823",
        }
      ],
      cart: []
    }
  },
  methods: {
    addToCart(product) {
      this.cart.push(product)
    }
  }
}
</script>
<style>
/* Global styles */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: sans-serif;
}

/* Header styles */
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #222;
  padding: 1rem;
  position: relative;
}

.contact {
  display: flex;
  gap: 1rem;
}

.contact a {
  color: #fff;
  text-decoration: none;
  font-weight: bold;
  transition: opacity 0.2s ease-in-out;
}

.contact a:hover {
  opacity: 0.8;
}

.logo img {
  display: block;
  max-width: 100%;
}

.shop {
  position: absolute;
  right: 1rem;
  display: flex;
  align-items: center;
  gap: 0.5rem;
  color: #fff;
}

.shop span {
  background-color: #ff6b6b;
  color: #fff;
  padding: 0.1rem 0.5rem;
  border-radius: 50%;
  font-size: 0.8rem;
}

/* Product list styles */
.product-list {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin: 2rem 0;
}

.product {
  flex-basis: calc(50% - 0.5rem);
  background-color: #f2f2f2;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 0.5rem;
}

.product img {
  max-width: 100%;
  height: auto;
  margin-bottom: 0.5rem;
}

.product p {
  font-size: 1.1rem;
  font-weight: bold;
  text-align: center;
  margin-bottom: 0.5rem;
}

.product button {
  background-color: #ff6b6b;
  color: #fff;
  padding: 0.5rem 1rem;
  border: none;
  border-radius: 0.25rem;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.2s ease-in-out;
}

.product button:hover {
  background-color: #d80000;
}
</style>