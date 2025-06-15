<template>
  <div class="max-w-7xl mx-auto p-4">
    <table class="min-w-full bg-gray-800 text-gray-100">
      <thead>
        <tr>
          <th class="p-4 border-b border-gray-600 text-left">ID</th>
          <th class="p-4 border-b border-gray-600 text-left">Name</th>
          <th class="p-4 border-b border-gray-600 text-left">City</th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="student in students"
          :key="student.id"
          class="hover:bg-gray-700"
        >
          <td class="p-4 border-b border-gray-600">{{ student.id }}</td>
          <td class="p-4 border-b border-gray-600">{{ student.name }}</td>
          <td class="p-4 border-b border-gray-600">{{ student.city }}</td>
        </tr>
      </tbody>
      <tfoot>
        <tr>
          <td class="p-4 border-b border-gray-600"></td>
          <td class="p-4 border-b border-gray-600"></td>
          <td class="p-4 border-b border-gray-600">
            <!-- <button @click="tableVisible = false">add</button> -->
          </td>
        </tr>
      </tfoot>
    </table>

    <AddButton @addstudent="studentAdded"></AddButton>
  </div>
</template>

<script>
import AddButton from "./AddButton.vue";
export default {
  components: { AddButton },
  async created() {
    let response = await fetch(this.gurl);
    this.students = await response.json();
  },
  data: () => ({
    students: [],
    gurl: "http://localhost:3000/students",
  }),
  methods: {
    studentAdded(newStudent) {
      const data = fetch(this.gurl, {
        method: "POST",
        body: JSON.stringify(newStudent),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
        },
      })
        .then((data) => data.status)
        .catch((err) => console.log(err));
      console.log(newStudent);
    },
  },
};
</script>
