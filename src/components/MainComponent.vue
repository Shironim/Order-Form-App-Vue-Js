<template>
  <section class="section">
    <div class="container">
      <div class="row">
        <div class="col-sm-12">
          <div class="text-right">
            <a href="#">
              <button
                :class="{ 'btn-primary' : layout == 'list' }"
                @click="layout = 'list'"
                class="btn"
              >List View</button>
            </a>
            <a href="#">
              <button
                :class="{ 'btn-primary' : layout == 'grid' }"
                @click="layout = 'grid'"
                class="btn"
              >Grid View</button>
            </a>
          </div>
        </div>
      </div>
      <!-- Akan Ditampilkan Ketika layout Grid -->
      <div v-if="layout === 'grid'" class="grid">
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
      <div v-if="layout === 'list'" class="list">
        <div class="row">
          <div v-for="product in products"
            :key="product.id"
            @click="toogleActive(product)" 
            class="col-sm-6 card-col">
            <div class="card" :class="{ 'is-active': product.active }">
              <div class="row mr-0 ml-0">
                <div class="col p-0">
                  <div class="card-header">
                    <img class="card-img-top" :src="product.image" alt="Card image cap">
                  </div>
                </div>
                <div class="col d-flex align-self-center">
                  <div class="card-body">
                    <div class="card-caption d-flex justify-content-between mb-4">
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
          <tr  v-for="menu in menuPilihan" :key="menu.id">
            <th scope="row">#</th>
            <td>{{ menu.name }}</td>
            <td>{{ menu.price }}</td>
            <td>1 Porsi</td>
            <td>{{ menu.price }}</td>
          </tr>
          <tr>
            <th scope="row">#</th>
            <td colspan="3"></td>
            <th><h3>Total Harga</h3></th>
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
  data: function() {
    return {
      // Mode layout: "list" dan "grid"
      layout: "grid"
    };
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
    },
    
  },
  filters: {
    currency: function(value) {
      return "Rp " + value.toFixed(2);
    }
  },
  computed: {
    // Computed property untuk menyimpan produk-produk yang sesuai dengan searchTermss
    menuPilihan: function () {
      return this.products.filter(function (product) {
        if (product.active) {
          return product;
        }
      });

    }
  }
};
</script>