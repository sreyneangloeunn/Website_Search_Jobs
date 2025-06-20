<template>
  <div class="max-w-7xl mx-auto mt-8 px-4">
    <!-- Title -->
    <div class="max-w-7xl mx-auto px-4 mt-10">
  <div class="flex flex-col md:flex-row md:justify-between items-center mb-6 gap-4">
    <h2 class="text-4xl font-extrabold text-blue-800 flex items-center gap-3">
      <svg class="w-10 h-10 text-blue-600" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
      </svg>
      User List
    </h2>

    <input
      type="search"
      placeholder="Search by name or job title"
      class="w-full md:w-64 px-4 py-2 border border-gray-300 rounded-md focus:outline-none focus:ring-2 focus:ring-blue-400 focus:border-blue-400"
      aria-label="Search users"
      v-model="searchQuery"
    />
  </div>

 
</div>


    <div class="overflow-x-auto shadow-lg rounded-lg border border-gray-300">
      <table class="min-w-full border-collapse text-left">
        <thead class="bg-blue-700 text-white">
          <tr>
            <th class="p-3 border border-gray-300">Avatar</th> <!-- New column -->
            <th class="p-3 border border-gray-300">Name</th>
            <th class="p-3 border border-gray-300">Email</th>
            <th class="p-3 border border-gray-300">Province</th>
            <th class="p-3 border border-gray-300">Job Title</th>
            <th class="p-3 border border-gray-300">Phone</th>
            <th class="p-3 border border-gray-300">Status</th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="(user, index) in users"
            :key="index"
            class="even:bg-gray-50 hover:bg-blue-100 transition-colors duration-200"
          >
            <td class="p-3 border border-gray-300">
              <img
                :src="user.avatar"
                :alt="user.name + ' avatar'"
                class="w-10 h-10 rounded-full object-cover"
              />
            </td>
            <td class="p-3 border border-gray-300 font-medium text-gray-800">{{ user.name }}</td>
            <td class="p-3 border border-gray-300 text-gray-600">{{ user.email }}</td>
            <td class="p-3 border border-gray-300">{{ user.province }}</td>
            <td class="p-3 border border-gray-300">{{ user.jobTitle }}</td>
            <td class="p-3 border border-gray-300">{{ user.phone }}</td>
            <td class="p-3 border border-gray-300">
              <span 
                :class="{
                  'bg-green-200 text-green-800 px-2 py-1 rounded-full text-xs font-semibold': user.status === 'Active',
                  'bg-red-200 text-red-800 px-2 py-1 rounded-full text-xs font-semibold': user.status === 'Inactive',
                  'bg-yellow-200 text-yellow-800 px-2 py-1 rounded-full text-xs font-semibold': user.status === 'Pending'
                }"
              >
                {{ user.status }}
              </span>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script setup>
const users = [
  {
    avatar: 'https://randomuser.me/api/portraits/men/10.jpg',
    name: 'John Doe',
    email: 'john@example.com',
    province: 'Ontario',
    jobTitle: 'Frontend Developer',
    phone: '123-456-7890',
    status: 'Active'
  },
  {
    avatar: 'https://randomuser.me/api/portraits/women/21.jpg',
    name: 'Jane Smith',
    email: 'jane@example.com',
    province: 'Quebec',
    jobTitle: 'Backend Developer',
    phone: '987-654-3210',
    status: 'Inactive'
  },
  {
    avatar: 'https://randomuser.me/api/portraits/men/45.jpg',
    name: 'Carlos Mendez',
    email: 'carlos@example.com',
    province: 'British Columbia',
    jobTitle: 'Full Stack Developer',
    phone: '555-123-4567',
    status: 'Active'
  },
  {
    avatar: 'https://randomuser.me/api/portraits/women/55.jpg',
    name: 'Emily Zhang',
    email: 'emily@example.com',
    province: 'Alberta',
    jobTitle: 'UI/UX Designer',
    phone: '444-987-6543',
    status: 'Pending'
  },
  {
    avatar: 'https://randomuser.me/api/portraits/men/32.jpg',
    name: 'Mohammed Ali',
    email: 'mohammed@example.com',
    province: 'Manitoba',
    jobTitle: 'DevOps Engineer',
    phone: '333-222-1111',
    status: 'Active'
  },
  {
    avatar: 'https://randomuser.me/api/portraits/women/33.jpg',
    name: 'Sofia Lopez',
    email: 'sofia@example.com',
    province: 'Nova Scotia',
    jobTitle: 'QA Engineer',
    phone: '777-888-9999',
    status: 'Active'
  },
  {
    avatar: 'https://randomuser.me/api/portraits/men/60.jpg',
    name: 'David Kim',
    email: 'david@example.com',
    province: 'Saskatchewan',
    jobTitle: 'Backend Developer',
    phone: '222-333-4444',
    status: 'Inactive'
  },
  {
    avatar: 'https://randomuser.me/api/portraits/women/70.jpg',
    name: 'Anna Müller',
    email: 'anna@example.com',
    province: 'New Brunswick',
    jobTitle: 'Frontend Developer',
    phone: '666-555-4444',
    status: 'Active'
  }
]
</script>

<style scoped>
td, th {
  vertical-align: middle;
}

tbody tr:hover {
  cursor: pointer;
}
</style>
