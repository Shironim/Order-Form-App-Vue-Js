<template>
  <form id="app" v-cloak>
    <h1>Switchable Grid</h1>
    <div class="controls">
      <!-- Dua tombol ini untuk berganti antar layout,
      sehingga hanya elemen ul yang sesuai yang tampil.-->
      <a :class="{ 'active': layout == 'list' }" @click="layout = 'list'">List View</a>
      <a :class="{ 'active': layout == 'grid' }" @click="layout = 'grid'">Grid View</a>
    </div>

    <!-- Dua layout yang kita punya, yang tampil hanya apabila isi dari model layout sesuai. -->
    <ul v-if="layout === 'grid'" class="grid">
      <li v-for="product in products" v-bind:key="product.id">
        <img :src="product.image.medium" />
      </li>
    </ul>

    <ul v-if="layout === 'list'" class="list">
      <li v-for="product in products" v-bind:key="product.id">
        <img :src="product.image.small" />
        <p>{{ product.name }}</p>
      </li>
    </ul>
    <FormOrder />
  </form>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import CardLogin from './components/CardLogin.vue'
import FormOrder from "./components/FormOrder.vue";

export default {
  name: "App",
  components: {
    // HelloWorld
    // CardLogin,
    FormOrder
  },
  // Ini adalah model.
  // Definisikan properti lalu beri nilai awal.
  data: function() {
    return {
      // Mode layout: 'list' dan 'grid'
      layout: "list",
      products: [
        {
          id: 1,
          name: "Cappucino",
          price: 35000,
          active: true,
          image: {
            medium: "https://i.imgur.com/Tp3FP7R.jpg",
            small: "https://i.imgur.com/cm1QpWn.jpg"
          }
        },
        {
          id: 2,
          name: "Green Tea Latte",
          price: 40000,
          active: true,
          image: {
            medium: "https://i.imgur.com/aUGBfvI.jpg",
            small: "https://i.imgur.com/mWsFDbO.jpg"
          }
        },
        {
          id: 3,
          name: "Fish and Chips",
          price: 50000,
          active: true,
          image: {
            medium: "https://i.imgur.com/ItOox1N.jpg",
            small: "https://i.imgur.com/keKToBD.jpg"
          }
        },
        {
          id: 4,
          name: "Tuna Sandwich",
          price: 45000,
          active: true,
          image: {
            medium: "https://i.imgur.com/OrrDIBd.jpg",
            small: "https://i.imgur.com/vKhChve.jpg"
          }
        },
        {
          id: 5,
          name: "Mineral Water",
          price: 8000,
          active: false,
          image: {
            medium: "https://i.imgur.com/9MGbQLR.jpg",
            small: "https://i.imgur.com/WIzJWes.jpg"
          }
        },
        {
          id: 6,
          name: "Frence Fries",
          price: 18000,
          active: false,
          image: {
            medium: "https://i.imgur.com/6CEZAgt.jpg",
            small: "https://i.imgur.com/9aKYsOl.jpg"
          }
        }
      ]
    };
  },
  methods: {
        toggleActive: function(product) {
          product.active = !product.active;
        },
        total: function() {
          var total = 0;
          this.products.forEach(function(product) {
            if (product.active) {
              total += product.price;
            }
          });

          return total;
        }
      },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  font-family: sans-serif;
  text-align: center;
  color: #333;
}

a,
a:visited {
  outline: none;
}

a:hover {
  text-decoration: none;
}

#app {
  position: relative;
  min-height: 500px;
  margin: 30px auto;
  padding: 32px;
  background: #f5f5f5;
  border: 1px solid #ddd;
  border-radius: 3px;
  box-shadow: 1px 1px 1px #ddd;
}

form {
  width: 500px;
}

.controls {
  width: 436px;
  margin: 0 auto;
  margin-bottom: 12px;
  text-align: right;
}

.controls a {
  display: inline-block;
  padding: 8px 12px;
  border: 1px solid #ddd;
  background: #fff;
  border-radius: 3px;
}

.controls a:hover {
  background: #f5f5f5;
  cursor: pointer;
}

.controls a.active {
  background: #4e8af8;
  border-color: #3176f7;
  color: #f5f5f5;
}

.controls a.active:hover {
  background: #2d70ec;
}

ul {
  list-style: none;
}

ul:after {
  display: table;
  content: "";
  clear: both;
}

ul li {
  margin-bottom: 8px;
  border: 1px solid #ddd;
  padding: 12px 16px;
  background: #fff;
  font-weight: bold;
  text-align: left;
  border-radius: 3px;
}

/*-------------------------
    List layout
--------------------------*/

ul.list {
  list-style: none;
  width: 436px;
  margin: 0 auto;
  text-align: left;
}

ul.list li {
  border-bottom: 1px solid #ddd;
  padding: 10px;
  overflow: hidden;
}

ul.list li img {
  width: 120px;
  height: 120px;
  float: left;
  border: none;
}

ul.list li p {
  margin-left: 135px;
  font-weight: bold;
  color: #6e7a7f;
}

/*-------------------------
  Grid layout
--------------------------*/

ul.grid {
  list-style: none;
  width: 436px;
  margin: 0 auto;
  text-align: left;
}

ul.grid li {
  padding: 2px;
  float: left;
}

ul.grid li:nth-child(odd) {
  margin-right: 8px;
}

ul.grid li img {
  width: 208px;
  height: 208px;
  object-fit: cover;
  display: block;
  border: none;
}
</style>
