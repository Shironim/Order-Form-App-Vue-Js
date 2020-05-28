<template>
  <div class="app">
    <nav class="navbar navbar-expand-lg">
      <div class="container">
        <a class="navbar-brand text-white font-weight-bold" href="#">Order Form App</a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav mr-auto">
            <!-- <li class="nav-item active">
            <a class="nav-link" href="#">Home </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Link</a>
            </li>-->
            <!-- <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-toggle="dropdown"
              aria-haspopup="true" aria-expanded="false">
              Dropdown
            </a>
            <div class="dropdown-menu" aria-labelledby="navbarDropdown">
              <a class="dropdown-item" href="#">Action</a>
              <a class="dropdown-item" href="#">Another action</a>
              <div class="dropdown-divider"></div>
              <a class="dropdown-item" href="#">Something else here</a>
            </div>
            </li>-->
          </ul>
          <form class="form-inline my-2 my-lg-0">

            <!-- Buat binding antara elemen input dengan model searchTerms -->
            <input
              v-model="searchTerms"
              class="form-control mr-sm-2"
              type="search"
              placeholder="Apa yang kamu cari ?"
              aria-label="Search"
            />
            <button class="btn my-2 my-sm-0 text-black" type="submit">Search</button>
          </form>
        </div>
      </div>
    </nav>

    <MainComponent :products="filteredProducts" />

    <FooterComponent />
  </div>
</template>

<script>
// import CardLogin from './components/CardLogin.vue'
// import NavComponent from "./components/NavComponent";
import MainComponent from "./components/MainComponent";
import FooterComponent from "./components/FooterComponent";

export default {
  name: "App",
  components: {
    // NavComponent,
    MainComponent,
    FooterComponent
  },
  data() {
    return {
      // Ini adalah model.
      // Definisikan properti lalu beri nilai awal.

      // Search item
      searchTerms: "",
      // properti products tipe array
      products: [
        {
          id: 1,
          name: "Rendang paha ayam organik.",
          price: 25000,
          active: false,
          image:
            "https://cdn-brilio-net.akamaized.net/news/2019/07/23/167723/1069955-1000xauto-resep-masakan-sederhana-menu-sehari-hari.jpg"
        },
        {
          id: 2,
          name: "Oseng kacang panjang.",
          price: 22000,
          active: false,
          image:
            "https://cdn-brilio-net.akamaized.net/news/2019/07/23/167723/1069960-1000xauto-resep-masakan-sederhana-menu-sehari-hari.jpg"
        },
        {
          id: 3,
          name: "Indomie seblak macaroni.",
          price: 18000,
          active: false,
          image:
            "https://cdn-brilio-net.akamaized.net/news/2019/07/23/167723/1069956-1000xauto-resep-masakan-sederhana-menu-sehari-hari.jpg"
        },
        {
          id: 4,
          name: "Penyetan sambel terasi udang.",
          price: 16000,
          active: false,
          image:
            "https://cdn-brilio-net.akamaized.net/news/2019/07/23/167723/1069957-1000xauto-resep-masakan-sederhana-menu-sehari-hari.jpg"
        },
        {
          id: 5,
          name: "Tumis jamur tiram.",
          price: 16000,
          active: true,
          image:
            "https://cdn-brilio-net.akamaized.net/news/2019/07/23/167723/1069958-1000xauto-resep-masakan-sederhana-menu-sehari-hari.jpg"
        },
        {
          id: 6,
          name: "Capcay goreng.",
          price: 18000,
          active: false,
          image:
            "https://cdn-brilio-net.akamaized.net/news/2019/07/23/167723/1069959-resep-masakan-sederhana-menu-sehari-hari.jpg"
        }
      ]
    };
  },
  computed: {
    // Computed property untuk menyimpan produk-produk yang sesuai dengan searchTermss
    filteredProducts: function () {
      var terms = this.searchTerms.trim().toLowerCase();

      // if (!this.searchTerms.length) {
      //   return this.products;
      // }

      return this.products.filter(function (product) {
        if (product.name.toLowerCase().indexOf(terms) !== -1) {
          return product;
        }
      });
    }
  }
};
</script>

<style>
/* @import 'bootstrap/dist/css/bootstrap.css'; */
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
