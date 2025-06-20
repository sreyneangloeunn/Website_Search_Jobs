<template>
  <div class="max-w-3xl mx-auto mt-8 p-6 bg-white rounded-lg shadow-md">
    <h2 class="text-3xl font-extrabold mb-4 text-blue-800">👤 Register a New Team Member</h2>
    <p class="text-gray-600 mb-6">
      Fill out the form below to add a new team member to our system. This helps us keep our team organized and ensures everyone stays connected!
    </p>

    <form @submit.prevent="addUser" class="grid grid-cols-1 md:grid-cols-2 gap-6">
      <!-- Name -->
      <div class="flex flex-col">
        <label for="name" class="mb-1 font-semibold text-gray-700">Name</label>
        <input
          v-model="newUser.name"
          id="name"
          type="text"
          placeholder="Full name"
          class="p-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-400 focus:border-blue-400 transition"
          required
          autocomplete="name"
          aria-describedby="nameHelp"
        />
      </div>

      <!-- Email -->
      <div class="flex flex-col">
        <label for="email" class="mb-1 font-semibold text-gray-700">Email</label>
        <input
          v-model="newUser.email"
          id="email"
          type="email"
          placeholder="example@domain.com"
          class="p-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-400 focus:border-blue-400 transition"
          required
          autocomplete="email"
          aria-describedby="emailHelp"
        />
      </div>

      <!-- Province -->
      <div class="flex flex-col">
        <label for="province" class="mb-1 font-semibold text-gray-700">Province</label>
        <input
          v-model="newUser.province"
          id="province"
          type="text"
          placeholder="e.g., Ontario"
          class="p-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-400 focus:border-blue-400 transition"
          required
        />
      </div>

      <!-- Job Title -->
      <div class="flex flex-col">
        <label for="jobTitle" class="mb-1 font-semibold text-gray-700">Job Title</label>
        <input
          v-model="newUser.jobTitle"
          id="jobTitle"
          type="text"
          placeholder="e.g., Frontend Developer"
          class="p-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-400 focus:border-blue-400 transition"
          required
        />
      </div>

      <!-- Phone -->
      <div class="flex flex-col">
        <label for="phone" class="mb-1 font-semibold text-gray-700">Phone</label>
        <input
          v-model="newUser.phone"
          id="phone"
          type="tel"
          placeholder="e.g., +1 234 567 890"
          class="p-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-400 focus:border-blue-400 transition"
          required
          autocomplete="tel"
        />
      </div>

      <!-- Status -->
      <div class="flex flex-col">
        <label for="status" class="mb-1 font-semibold text-gray-700">Status</label>
        <select
          v-model="newUser.status"
          id="status"
          class="p-3 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-400 focus:border-blue-400 transition"
          required
        >
          <option value="Active">Active</option>
          <option value="Inactive">Inactive</option>
        </select>
      </div>

      <!-- Image Upload -->
      <div class="flex flex-col md:col-span-2">
        <label for="avatar" class="mb-1 font-semibold text-gray-700">Profile Image</label>
        <input
          id="avatar"
          type="file"
          accept="image/*"
          @change="onFileChange"
          class="p-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-400 focus:border-blue-400 transition"
        />
        <div v-if="newUser.avatar" class="mt-3">
          <p class="text-sm text-gray-600 mb-1">Preview:</p>
          <img
            :src="newUser.avatar"
            alt="Image preview"
            class="w-24 h-24 rounded-full object-cover border border-gray-300"
          />
        </div>
      </div>

      <!-- Submit button full width on mobile -->
      <div class="md:col-span-2 flex justify-end">
        <button
          type="submit"
          class="px-8 py-3 bg-blue-700 text-white font-semibold rounded-md shadow-md hover:bg-blue-800 focus:outline-none focus:ring-4 focus:ring-blue-300 transition"
        >
          Add User
        </button>
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const newUser = ref({
  name: '',
  email: '',
  province: '',
  jobTitle: '',
  phone: '',
  status: 'Active',
  avatar: null // will hold image data URL
})

const onFileChange = (event) => {
  const file = event.target.files[0]
  if (!file) {
    newUser.value.avatar = null
    return
  }
  // Simple file type check
  if (!file.type.startsWith('image/')) {
    alert('Please select a valid image file.')
    event.target.value = ''
    return
  }

  const reader = new FileReader()
  reader.onload = (e) => {
    newUser.value.avatar = e.target.result
  }
  reader.readAsDataURL(file)
}

const addUser = () => {
  alert(`User added:\nName: ${newUser.value.name}\nEmail: ${newUser.value.email}`)
  // Reset form
  newUser.value = {
    name: '',
    email: '',
    province: '',
    jobTitle: '',
    phone: '',
    status: 'Active',
    avatar: null
  }
}
</script>

<style scoped>
input,
select {
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
}
</style>
