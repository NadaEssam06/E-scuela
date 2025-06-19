<template>
  <div class="flex flex-col min-h-screen">
    <navbar></navbar>

    <router-view></router-view>

    <Footer></Footer>
  </div>
</template>

<script>
import navbar from "./components/navbar.vue";
import Footer from "./components/Footer.vue";
import Contact from "./components/Contact.vue";
import Home from "./components/Home.vue";
import router from "./routes/index.vue";

export default {
  name: "App",
  components: {
    navbar,
    Home,
    Footer,
    Contact,
    router,
  },
};
</script>
