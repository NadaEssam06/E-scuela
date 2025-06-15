<script>
import Contact from "@/components/Contact.vue";
import Home from "@/components/Home.vue";
import { createRouter, createWebHashHistory } from "vue-router";
const routes = [
  {
    path: "/",
    component: Home,
  },
  {
    path: "/contact",
    component: Contact,
  },
  {
    path: "/student",
    component: Home,
  },
];
</script>
