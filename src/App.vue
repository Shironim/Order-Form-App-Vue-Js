<template>
  <div class="app">
    <NavComponent />
    <MainComponent />
    <FormOrderComponent />
    <FooterComponent />
  </div>
</template>

<script>
// import CardLogin from './components/CardLogin.vue'
import NavComponent from "./components/NavComponent";
import MainComponent from "./components/MainComponent";
import FormOrderComponent from "./components/FormOrderComponent";
import FooterComponent from "./components/FooterComponent";

export default {
  name: "App",
  components: {
    NavComponent,
    MainComponent,
    FormOrderComponent,
    FooterComponent,
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
