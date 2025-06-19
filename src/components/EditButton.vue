<template>
  <div>
    <!-- Button to show modal -->
    <button
      @click="openModal"
      class="px-4 py-2 font-semibold text-gray-900 bg-gray-100 rounded-md shadow-md hover:bg-gray-200 transition"
    >
      Edit
    </button>

    <!-- Modal -->
    <dialog
      ref="modal"
      class="bg-gray-800 p-6 rounded-lg shadow-md space-y-6 max-w-md"
    >
      <h2 class="text-2xl font-semibold text-gray-100 mb-4">Edit Student</h2>

      <div class="flex flex-col space-y-4">
        <div>
          <label for="stdId" class="block text-gray-400 mb-1 font-semibold">
            ID
          </label>
          <input
            disabled
            id="stdId"
            type="number"
            v-model="editableStd.id"
            class="w-full p-2 bg-gray-900 text-gray-100 border border-gray-600 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>

        <div>
          <label for="stdName" class="block text-gray-400 mb-1 font-semibold">
            Name
          </label>
          <input
            id="stdName"
            type="text"
            v-model="editableStd.name"
            class="w-full p-2 bg-gray-900 text-gray-100 border border-gray-600 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>

        <div>
          <label for="stdCity" class="block text-gray-400 mb-1 font-semibold">
            City
          </label>
          <input
            id="stdCity"
            type="text"
            v-model="editableStd.city"
            class="w-full p-2 bg-gray-900 text-gray-100 border border-gray-600 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-500"
          />
        </div>
      </div>

      <div class="flex justify-end space-x-2 mt-6">
        <button
          @click="closeModal"
          class="px-4 py-2 font-semibold text-gray-100 bg-gray-600 rounded-md shadow-md hover:bg-gray-500 transition"
        >
          Cancel
        </button>

        <button
          @click="editData"
          class="px-4 py-2 font-semibold text-gray-900 bg-blue-500 rounded-md shadow-md hover:bg-blue-400 transition"
        >
          Save
        </button>
      </div>
    </dialog>
  </div>
</template>

<script>
export default {
  name: "EditButton",
  props: ["std"],
  data() {
    return {
      editableStd: { ...this.std },
    };
  },
  methods: {
    openModal() {
      this.editableStd = { ...this.std }; // Reset to original
      this.$refs.modal.showModal();
    },
    closeModal() {
      this.$refs.modal.close();
    },
    async editData() {
      try {
        const response = await fetch(
          `http://localhost:3000/students/${this.editableStd.id}`,
          {
            method: "PATCH",
            body: JSON.stringify(this.editableStd),
            headers: { "Content-Type": "application/json; charset=UTF-8" },
          }
        );
        if (!response.ok) {
          console.error("Failed to update.");
          return;
        }
        console.log(await response.json());

        this.closeModal();
        this.$emit("update", this.editableStd);
      } catch (err) {
        console.error(err);
      }
    },
  },
};
</script>
