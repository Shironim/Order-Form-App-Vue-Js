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
body{
  font-family: 'Poppins', sans-serif;
}
.navbar{
  background: #F2A034;
  color: white;
  -webkit-box-shadow: 0px 4px 20px 2px rgba(0,0,0,0.2);
  -moz-box-shadow: 0px 4px 20px 2px rgba(0,0,0,0.2);
  box-shadow: 0px 4px 20px 2px rgba(0,0,0,0.2);
}
.card:hover{
  -webkit-box-shadow: 5px 8px 20px 1px rgba(0,0,0,0.26);
  -moz-box-shadow: 5px 8px 20px 1px rgba(0,0,0,0.26);
  box-shadow: 5px 8px 20px 1px rgba(0,0,0,0.26);
  transition: 0.8s all;
  -webkit-transition: 0.8s all;
  -moz-transition: 0.8s all;
  -ms-transition: 0.8s all;
  -o-transition: 0.8s all;
}
.is-active{
  -webkit-box-shadow: 5px 8px 20px 1px rgba(155,160,235,1);
  -moz-box-shadow: 5px 8px 20px 1px rgba(155,160,235,1);
  box-shadow: 5px 8px 20px 1px rgba(155,160,235,1);
}
.card{
  transition: 0.8s all;
  -webkit-transition: 0.8s all;
  -moz-transition: 0.8s all;
  -ms-transition: 0.8s all;
  -o-transition: 0.8s all;
  background-color: #FED766;
  border: none;
}
.card-body{
  padding: 1rem;
}
/* List Layout */
.list .card-body{
  padding: 0;
}
.list .card-caption .name{
  font-size: 20px;
}
.list img{
  height: 200px;
  width: 100%;
}
.list .card-caption{
  height: 90px;
}
.list .card-caption .name{
  font-size: 16px;
  font-weight: lighter;
  width: 60%;
}
.list .card-caption .price{
  font-size: 16px;
  font-weight: bold;
  width: 40%;
  justify-content: end;

}
.list .card-caption .card-text{
  margin: 0 !important;
  display: flex;
  align-items: center;
}
.list .card-body{
  height: 150px;
}
/* End List Layout */
/* Grid Layout */
.grid img{
  height: 340px;
  width: 100%;
}
.grid .card-caption{
  height: 50px;
}
.grid .card-caption .name{
  font-size: 16px;
  font-weight: lighter;
  width: 60%;
}
.grid .card-caption .price{
  font-size: 18px;
  font-weight: bold;
  width: 40%;
  justify-content: end;

}
.grid .card-caption .card-text{
  margin: 0 !important;
  display: flex;
  align-items: center;
}
.grid .card-body{
  height: 150px;
}
/* End grid Layout */

.card-header{
  padding: 0;
}
.card-col{
  padding-right: 15px;
  padding-left: 15px;
  padding-top: 15px;
  padding-bottom: 15px;
}

.card-caption{
  margin-bottom: 10px;
}
.card-btn .btn{
  padding: 6px 30px;
  background-color: #F2A034;
  color: white;
  font-weight: bold;
}
.total-price{
  font-size: 24px;
  font-weight: bold;
  letter-spacing: 1px;
}
.section{
  margin-top: 25px;
  margin-bottom: 15px;
}
.footer{
  padding: .5rem 1rem;
  background: #F2A034;
  color: #fff;
  text-align: right;
}
</style>
