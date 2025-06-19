<template>
  <!-- Open the modal using ID.showModal() method -->
  <button class="btn" onclick="my_modal_1.showModal()">Add</button>
  <dialog
    id="my_modal_1"
    class="modal bg-gray-800 p-6 rounded-lg shadow-md space-y-4 max-w-md"
  >
    <div class="modal-box">
      <h3 class="text-lg font-bold">Hello!</h3>
      <p class="py-4">Press ESC key or click the button below to close</p>
      <div class="modal-action">
        <label for="stdid" class="block text-gray-400 mb-1 font-semibold"
          >ID</label
        >
        <input
          id="title"
          v-model="std.id"
          class="w-full p-2 bg-gray-900 text-gray-100 border border-gray-600 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
        />
        <label for="stdname" class="block text-gray-400 mb-1 font-semibold"
          >Name</label
        >
        <input
          type="text"
          id="title"
          v-model="std.name"
          class="w-full p-2 bg-gray-900 text-gray-100 border border-gray-600 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
        />

        <label for="stdcity" class="block text-gray-400 mb-1 font-semibold"
          >City</label
        >
        <input
          type="text"
          id="title"
          v-model="std.city"
          class="w-full p-2 bg-gray-900 text-gray-100 border border-gray-600 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
        />
        <button @click="addStudent">add</button>
      </div>
    </div>
  </dialog>
</template>
<script>
export default {
  name: "AddBuuton",
  data: () => ({
    std: { id: "", name: "", city: "" },
  }),
  methods: {
    async addStudent() {
      const modal = document.getElementById("my_modal_1");

      this.$emit("addstudent", this.std);
      modal.close();
    },
  },
};
</script>
