<template>
  <table class="min-w-full border border-gray-300 rounded shadow-md">
    <thead class="bg-blue-600 text-white">
      <tr>
        <th class="py-2 px-4 text-left">Name</th>
        <th class="py-2 px-4 text-left">Email</th>
        <th class="py-2 px-4 text-left">Province</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(user, index) in users" :key="index" class="border-t">
        <td class="py-2 px-4">{{ user.name }}</td>
        <td class="py-2 px-4">{{ user.email }}</td>
        <td class="py-2 px-4">{{ user.province }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script setup>
defineProps({
  users: {
    type: Array,
    required: true
  }
})
</script>
