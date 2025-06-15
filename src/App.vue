<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div class="flex flex-col min-h-screen">
    <navbar></navbar>
    <Home></Home>

    <Contact></Contact>

    <Footer></Footer>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import navbar from "./components/navbar.vue";
import Footer from "./components/Footer.vue";
import Contact from "./components/Contact.vue";
import Home from "./components/Home.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    navbar,
    Home,
    Footer,
    Contact,
  },
};
</script>

<!-- <style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style> -->
