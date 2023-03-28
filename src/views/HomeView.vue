<template>
  <div id="app">
    <header>

      <div class="contact">
        <router-link to="/">Anasayfa</router-link>
        <router-link to="/about">Hakkımda</router-link>
      </div>

      <div class="logo">
        <img
          src="//cdn.shopify.com/s/files/1/0725/1201/2597/files/Fast_Find_1_photoAid-removed-background_1_1.png?v=1677014673&width=500"
          width="150" height="150" alt="">
      </div>

      <div class="shop">
        <i class="fa-solid fa-basket-shopping-simple">
          <span>{{ cart.length }}</span>
        </i>
      </div>
    </header>


    <div class="products">
      <div class="cart">
        <div class="cartimg">
          <img v-for="(images, index) in images" :src="images.src" alt="">
        </div>
        <div class="cart-desc">
          <p v-for="(product, index) in products" :key="index">
            {{ product.name }}
            <br>
            <button @click="addtocart(product)">Sepete Ekle</button>
          </p>
        </div>
      </div>
    </div>

    <section>
      <div class="womenproducts">
        <div class="cart">
          <div class="cartimg">
            <img v-for="(images, index) in womanimages" :src="images.src" alt="">
          </div>
          <div class="cart-desc">
            <p v-for="(product, index) in products" :key="index">
            {{ product.name }}
            <br>
            <button @click="addtocart(product)">Sepete Ekle</button>
          </p>
          </div>
        </div>
      </div>
    </section>

  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        { name: "New short-sleeved printed shirt men and women casual beach clothes1" },
        { name: "New short-sleeved printed shirt men and women casual beach clothes2" },
        { name: "New short-sleeved printed shirt men and women casual beach clothes3" },
        { name: "New short-sleeved printed shirt men and women casual beach clothes4" },
        { name: "New short-sleeved printed shirt men and women casual beach clothes4" },
      ],
      images: [
        { src: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Hcb02a9cd42164e6e9c00d88d56e14088u.jpg?v=1677236060&width=823" },
        { src: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Hcb02a9cd42164e6e9c00d88d56e14088u.jpg?v=1677236060&width=823" },
        { src: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/H02ca386358a4416d9151fee22ab96dd2b.jpg?v=1677009630&width=823" },
        { src: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/S730d72a308414fb796aebe7e02a35a8ck.jpg?v=1677010854&width=823" },
        { src: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Sa8041d0da32a40eba324b01da56fd59ad.jpg?v=1677010912&width=823" },
      ],
      womanimages: [
        { src: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/H6e89874e7a424b9885840df26ce85756L.jpg?v=1676660857&width=823" },
        { src: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Hd1b6394dfdfa4c268ebb9aa9e39d1f64w.jpg?v=1677002289&width=823" },
        { src: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/He07f71f39b6b4132a150dff4c7aed6f2B.jpg?v=1677006677&width=823" },
        { src: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Sbfd9f31cfd8e4741b86a946151b6050a8.jpg?v=1677008100&width=823" },
        { src: "https://cdn.shopify.com/s/files/1/0725/1201/2597/products/Sa0810609161c4d2986a0c85fc9379e69y.jpg?v=1677006876&width=823" },
      ],
      cart: []
    }
  },
  methods: {
    addtocart: function (product) {
      this.cart.push(product)
    }
  }
}
</script>
<style>
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

body {
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
  background-color: rgb(12, 31, 45);
}

header {
  position: fixed;
  top:0;
  opacity: 0.8;
  display: flex;
  height: 115px;
  width: 100%;
  justify-content: space-around;
  align-items: center;
  background-color: rgba(18, 48, 69, 1);
}



.contact a {
  font-size: 17px;
  margin-left: 20px;
  color: white;
  text-decoration: none;
}

.logo img {
  width: 100px;
  height: 100px;
}


.shop i {
  font-size: 20px;
  color: white;
  margin: 50px;
}

.second-bar {
  margin-top: 150px;
}

.second-bar a {
  font-size: 17px;
  color: white;
  background-color: rgb(21, 61, 90);
  display: block;
  text-align: center;
  padding: 10px;
  text-decoration: none;
  opacity: 0.7;
}
.cart{
  margin-top: 150px;
}
.cartimg {
  margin: 20px;
}

.cartimg img {
  width: 250px;
  margin:18px;

}

.cart-desc {
  display: flex;
  justify-content: center;
  margin: 20px;
  color: white;
  text-align: center;
}

.cart button {
  border: none;
  padding: 0.5rem;
  width: 150px;
  margin-top: 20px;
}

.cart span {
  font-size: 13px;

}
</style>