<template>
  <div class="min-h-screen text-gray-100">
    <div class="max-w-7xl mx-auto py-12 px-4 sm:px-6 lg:px-8">
      <h1 class="text-3xl font-bold text-center mb-8 text-gray-900">
        Contact Us
      </h1>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
        <!-- Contact Form -->
        <div class="bg-gray-800 p-6 rounded-lg">
          <h2 class="text-xl font-semibold mb-4">Send us a message</h2>
          <form @submit.prevent="submitForm">
            <div class="mb-4">
              <label for="name" class="block text-gray-400 mb-2">Name</label>
              <input
                type="text"
                id="name"
                v-model="form.name"
                class="w-full p-2 bg-gray-700 text-gray-100 rounded border border-gray-600 focus:outline-none focus:border-gray-400"
                required
              />
            </div>
            <div class="mb-4">
              <label for="email" class="block text-gray-400 mb-2">Email</label>
              <input
                type="email"
                id="email"
                v-model="form.email"
                class="w-full p-2 bg-gray-700 text-gray-100 rounded border border-gray-600 focus:outline-none focus:border-gray-400"
                required
              />
            </div>
            <div class="mb-4">
              <label for="message" class="block text-gray-400 mb-2"
                >Message</label
              >
              <textarea
                id="message"
                v-model="form.message"
                class="w-full p-2 bg-gray-700 text-gray-100 rounded border border-gray-600 focus:outline-none focus:border-gray-400"
                rows="5"
                required
              ></textarea>
            </div>
            <button
              type="submit"
              class="bg-gray-600 hover:bg-gray-500 text-gray-100 py-2 px-4 rounded transition"
            >
              Send Message
            </button>
          </form>
        </div>

        <!-- Contact Information -->
        <div class="bg-gray-800 p-6 rounded-lg">
          <h2 class="text-xl font-semibold mb-4">Get in Touch</h2>
          <p class="text-gray-400 mb-4">
            We're here to help! Reach out to us via the form or use the contact
            details below.
          </p>
          <ul class="text-gray-400 space-y-2">
            <li>
              <span class="font-semibold">Email:</span>
              <a
                href="mailto:support@mycompany.com"
                class="hover:text-gray-200 transition"
              >
                support@mycompany.com
              </a>
            </li>
            <li>
              <span class="font-semibold">Phone:</span>
              <a href="tel:+1234567890" class="hover:text-gray-200 transition">
                +1 (234) 567-890
              </a>
            </li>
            <li>
              <span class="font-semibold">Address:</span>
              123 Business Ave, Suite 100, City, Country
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Contact",
  data() {
    return {
      form: {
        name: "",
        email: "",
        message: "",
      },
    };
  },
  methods: {
    submitForm() {
      // Placeholder for form submission logic
      console.log("Form submitted:", this.form);
      alert("Thank you for your message! We will get back to you soon.");
      this.form = { name: "", email: "", message: "" }; // Reset form
    },
  },
};
</script>
