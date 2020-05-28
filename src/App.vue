<template>
  <div class="app">
    <NavComponent />
    <MainComponent :products="products" />
    <FooterComponent />
  </div>
</template>

<script>
// import CardLogin from './components/CardLogin.vue'
import NavComponent from "./components/NavComponent";
import MainComponent from "./components/MainComponent";
import FooterComponent from "./components/FooterComponent";

export default {
  name: "App",
  components: {
    NavComponent,
    MainComponent,
    FooterComponent,
  },
  data() {
    return {
      // Ini adalah model.
      // Definisikan properti lalu beri nilai awal.

      // Mode layout: "list" dan "grid"
      layout: "list",
      // Search item
      searchTerms: "",
      // properti products tipe array
      products: [{
          id : 1,
          name: "Cappucino",
          price: 45000,
          active: false,
          image: "https://cdn.idntimes.com/content-images/community/2020/01/wesual-click-jkc1ul95ujq-unsplash-c16c534c3590f01842b0a7bc64bf05f4_600x400.jpg"
        }, {
          id : 2,
          name: "Green Tea Latte",
          price: 45000,
          active: false,
          image: "https://cdn.idntimes.com/content-images/community/2020/01/wesual-click-jkc1ul95ujq-unsplash-c16c534c3590f01842b0a7bc64bf05f4_600x400.jpg"
        },
        {
          id : 3,
          name: "Fish and Chips",
          price: 45000,
          active: false,
          image: "https://cdn.idntimes.com/content-images/community/2020/01/wesual-click-jkc1ul95ujq-unsplash-c16c534c3590f01842b0a7bc64bf05f4_600x400.jpg"
        },
        {
          id : 4,
          name: "Tuna Sandwich",
          price: 45000,
          active: true,
          image: "https://cdn.idntimes.com/content-images/community/2020/01/wesual-click-jkc1ul95ujq-unsplash-c16c534c3590f01842b0a7bc64bf05f4_600x400.jpg"
        },
        {
          id : 5,
          name: "Mineral Water",
          price: 45000,
          active: true,
          image: "https://cdn.idntimes.com/content-images/community/2020/01/wesual-click-jkc1ul95ujq-unsplash-c16c534c3590f01842b0a7bc64bf05f4_600x400.jpg"
        },
        {
          id : 6,
          name: "Frence Fries",
          price: 45000,
          active: false,
          image: "https://cdn.idntimes.com/content-images/community/2020/01/wesual-click-jkc1ul95ujq-unsplash-c16c534c3590f01842b0a7bc64bf05f4_600x400.jpg"
        },
      ]
    };
  },
}
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
