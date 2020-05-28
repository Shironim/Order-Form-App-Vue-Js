<template>
  <section class="section">
    <div class="container">
      <div class="row">
        <div class="col-sm-12">
          <div class="text-right">
            <a href="#">
              <button class="btn">List View</button>
            </a>
            <a href="#">
              <button class="btn btn-primary">Grid View</button>
            </a>
          </div>
        </div>
      </div>
      <div class="row">
        <div
          v-for="product in products"
          :key="product.id"
          @click="toogleActive(product)"
          class="col-sm-4 card-col"
        >
          <div class="card" :class="{ 'is-active': product.active }">
            <img class="card-img-top" :src="product.image" alt="Card image cap" />
            <div class="card-body">
              <div class="card-caption d-flex justify-content-between">
                <p class="card-text name">{{ product.name }}</p>
                <p class="card-text price">{{ product.price | currency }}</p>
              </div>
              <div class="card-btn text-center">
                <button type="button" class="btn">Buy</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="container">
      <h3>Total Pembelian</h3>
      <table class="table text-center">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Nama Menu</th>
            <th scope="col">Harga</th>
            <th scope="col">Jumlah</th>
            <th scope="col">Total</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <th scope="row">1</th>
            <td>Chesse Pizza</td>
            <td>$15</td>
            <td>1 Porsi</td>
            <td>$15</td>
          </tr>
          <tr>
            <th scope="row">2</th>
            <td>Chesse Pizza</td>
            <td>$15</td>
            <td>2 Porsi</td>
            <td>$30</td>
          </tr>
          <tr>
            <th scope="row">3</th>
            <td>Chesse Pizza</td>
            <td>$15</td>
            <td>3 Porsi</td>
            <td>$45</td>
          </tr>
          <tr>
            <th scope="row">#</th>
            <td colspan="3"></td>
            <th>Total Harga</th>
          </tr>
          <tr>
            <th scope="row">#</th>
            <td colspan="3"></td>
            <td class="total-price">{{ total() | currency }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>
</template>
<script>
// import MainViewComponent from "./MainViewComponent";
import FormOrderComponent from "./FormOrderComponent";

export default {
  name: "MainComponent",
  component: {
    FormOrderComponent
  },
  props: {
    products: {
      type: Array
    }
  },
  methods: {
    toogleActive: function(product) {
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
  filters: {
    currency: function(value) {
      return "Rp " + value.toFixed(2);
    }
  }
};
</script>