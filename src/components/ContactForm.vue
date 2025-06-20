<template>
  <form class="bg-white shadow-md rounded p-6 space-y-4" @submit.prevent="submitForm">
    <div>
      <label class="block text-gray-700 font-medium mb-1">Name</label>
      <input
        v-model="form.name"
        type="text"
        placeholder="Enter your name"
        class="w-full border border-gray-300 rounded px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
      />
    </div>

    <div>
      <label class="block text-gray-700 font-medium mb-1">Email</label>
      <input
        v-model="form.email"
        type="email"
        placeholder="Enter your email"
        class="w-full border border-gray-300 rounded px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
      />
    </div>

    <div>
      <label class="block text-gray-700 font-medium mb-1">Province</label>
      <select
        v-model="form.province"
        class="w-full border border-gray-300 rounded px-4 py-2 focus:outline-none focus:ring-2 focus:ring-blue-500"
      >
        <option disabled value="">Select a province</option>
        <option>Phnom Penh</option>
        <option>Siem Reap</option>
        <option>Battambang</option>
        <option>Kampong Cham</option>
        <option>Kandal</option>
      </select>
    </div>

    <button
      type="submit"
      class="bg-blue-600 text-white px-6 py-2 rounded hover:bg-blue-700 transition"
    >
      Submit
    </button>
  </form>
</template>

<script setup>
import { reactive } from 'vue'

const form = reactive({
  name: '',
  email: '',
  province: ''
})

function submitForm() {
  alert(`Submitted:\nName: ${form.name}\nEmail: ${form.email}\nProvince: ${form.province}`)
  form.name = ''
  form.email = ''
  form.province = ''
}
</script>
