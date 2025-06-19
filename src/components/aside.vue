<template>
  <aside>
    <ul class="flex flex-col justify-between items-center h-full p-4">
      <li>
        <router-link to="/" class="text-gray-400 hover:text-gray-200 transition"
          >Home</router-link
        >
      </li>
      <li>
        <a href="/#about" class="text-gray-400 hover:text-gray-200 transition">
          About
        </a>
      </li>
      <li>
        <router-link
          to="/contact"
          class="text-gray-400 hover:text-gray-200 transition"
          >Contact</router-link
        >
      </li>
    </ul>
  </aside>
</template>
<script>
export default {
  name: "Aside",
};
</script>
