<script>
import Contact from "@/components/Contact.vue";
import Home from "@/components/Home.vue";
import NotFound from "@/components/NotFound.vue";
import Student from "@/components/Student.vue";
import { createRouter, createWebHistory } from "vue-router";
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
  {
    path: "/student/:id",
    component: Student,
  },
  {
    path: "/:catchAll(.*)",
    component: NotFound,
  },
];
const router = createRouter({
  routes: routes,
  history: createWebHistory(),
});
export default router;
</script>
