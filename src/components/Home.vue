<template>
  <div class="flex flex1">
    <Aside class="w-1/8 p-4 m-4 bg-gray-800 text-gray-100"></Aside>
    <StudentTable class="flex-1 p-4"></StudentTable>
  </div>
</template>
<script>
import Aside from "./aside.vue";
import StudentTable from "./StudentTable.vue";
export default {
  name: "Home",
  components: {
    Aside,
    StudentTable,
  },
};
</script>
