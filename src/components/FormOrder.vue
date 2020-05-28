<template>
<div class="form-order" v-cloak>
  <h1>Pesanan</h1>
  <ul>
    <!-- Loop array products, beri handle klik, dan set atau hilangkan kelas is-active jika dibutuhkan -->
    <li v-for="product in products" v-on:click="toggleActive(product)" v-bind:class="{ 'is-active': product.active }" v-bind:key="product.id">
      <!-- Tampilkan nama dan harga barang. -->
      <!-- Gunakan currency filter yang telah kita definisikan. -->
      {{ product.name }}
      <span>{{ product.price | currency }}</span>
    </li>
  </ul>

  <div class="total">
    Total:
    <!-- Kalkulasi harga total. Lagi-lagi kita gunakan filter currency disini. -->
    <span>{{ total() | currency }}</span>
  </div>
</div>

</template>

<script>
export default {
  name : 'FormOrder',
  data: function() {
        return {
          // Definisikan model. View akan iterasi sebanyak model membuat elemen li untuk setiap produk.
          products: [{
            id : 1,
            name: 'Cappucino',
            price: 35000,
            active: true,
          }, {
            id : 2,
            name: 'Green Tea Latte',
            price: 40000,
            active: true
          }, {
            id : 3,
            name: 'Fish and Chips',
            price: 50000,
            active: true,
          }, {
            id : 4,
            name: 'Tuna Sandwich',
            price: 45000,
            active: true,
          }, {
            id : 5,
            name: 'Mineral Water',
            price: 8000,
            active: false,
          }, {
            id : 6,
            name: 'Frence Fries',
            price: 18000,
            active: false,
          }, ]
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
}
</script>

<style scoped>
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


form {
  width: 500px;
  background: #f5f5f5;
}

h1 {
  margin-bottom: 36px;
}

ul {
  width: 350px;
  margin: 0 auto;
  list-style: none;
}

ul li {
  margin-bottom: 8px;
  border: 1px solid #ddd;
  padding: 12px 16px;
  background: #fff;
  font-weight: bold;
  text-align: left;
}

ul li.is-active {
  color: #fff;
  background: #2ECC40;
  border-color: #27b137;
}

ul li.is-active:hover {
  background: #69d845;
}

ul li:hover {
  background: #f5f5f5;
  cursor: pointer;
}

ul li span {
  float: right;
}

.total {
  margin: 0 auto;
  width: 350px;
  padding: 20px 16px;
  font-weight: bold;
  font-size: 1.2em;
  text-align: left;
}

.total span {
  float: right;
}

</style>