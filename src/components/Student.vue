<template>
  <div class="bg-gray-900 min-h-screen text-gray-100">
    <div class="max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:px-8">
      <h1 class="text-3xl font-bold text-center mb-8">Student Details</h1>

      <div
        v-if="stdObj"
        class="bg-gray-800 p-6 rounded-lg shadow-md max-w-md mx-auto"
      >
        <h2 class="text-xl font-semibold mb-4 text-gray-200">
          {{ stdObj.name }}
        </h2>

        <div class="space-y-4">
          <div>
            <span class="font-semibold text-gray-400">ID: </span>
            <span class="text-gray-100">{{ stdObj.id }}</span>
          </div>
          <div>
            <span class="font-semibold text-gray-400">Name: </span>
            <span class="text-gray-100">{{ stdObj.name }}</span>
          </div>
          <div>
            <span class="font-semibold text-gray-400">City: </span>
            <span class="text-gray-100">{{ stdObj.city }}</span>
          </div>
        </div>

        <div class="flex space-x-4 mt-6">
          <edit-button :std="stdObj" @update="handleStudentUpdate" />

          <button
            @click="handleStudentDelete"
            class="px-4 py-2 font-semibold text-gray-100 bg-red-600 rounded-md shadow-md hover:bg-red-500 transition"
          >
            Delete
          </button>

          <router-link
            to="/student"
            class="px-4 py-2 font-semibold text-gray-100 bg-gray-600 rounded-md shadow-md hover:bg-gray-500 transition"
          >
            Back to Students
          </router-link>
        </div>
      </div>

      <div v-else class="text-center text-gray-400">
        <p>Student not found.</p>
        <router-link
          to="/student"
          class="mt-4 inline-block px-4 py-2 font-semibold text-gray-100 bg-gray-600 rounded-md shadow-md hover:bg-gray-500 transition"
        >
          Back to Students
        </router-link>
      </div>
    </div>
  </div>
</template>
<script>
import EditButton from "./EditButton.vue";

export default {
  name: "Student",
  components: {
    EditButton,
  },
  methods: {
    async handleStudentUpdate() {
      let response = await fetch(
        "http://localhost:3000/students/" + this.stdId
      );
      this.stdObj = await response.json();
    },
    async handleStudentDelete() {
      await fetch("http://localhost:3000/students/" + this.stdId, {
        method: "DELETE",
      });
      location.href = "/";
    },
  },
  data: () => ({
    stdId: "",
    stdObj: { id: "", name: "", city: "" },
  }),
  async created() {
    this.stdId = this.$route.params.id;
    let response = await fetch("http://localhost:3000/students/" + +this.stdId);
    this.stdObj = await response.json();
  },
};
</script>
