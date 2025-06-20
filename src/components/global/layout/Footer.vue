<template>
  <footer class="bg-gray-900 text-gray-300 py-12">
    <div class="max-w-6xl mx-auto px-4 grid grid-cols-1 md:grid-cols-3 gap-8">
      
      <!-- About Section -->
      <div>
        <h3 class="text-white text-xl font-semibold mb-4">{{ aboutTitle }}</h3>
        <p class="text-sm leading-relaxed">
          {{ aboutText }}
        </p>
      </div>
      
      <!-- Contact Section -->
      <div>
        <h3 class="text-white text-xl font-semibold mb-4">Contact</h3>
        <ul class="text-sm space-y-2">
          <li>Email: {{ email }}</li>
          <li>Phone: {{ phone }}</li>
          <li>Address: {{ address }}</li>
        </ul>
      </div>
      
      <!-- Social Links Section -->
      <div>
        <h3 class="text-white text-xl font-semibold mb-4">Follow Us</h3>
        <div class="flex space-x-4">
          <a :href="facebook" class="hover:text-white">Facebook</a>
          <a :href="twitter" class="hover:text-white">Twitter</a>
          <a :href="linkedin" class="hover:text-white">LinkedIn</a>
          <a :href="instagram" class="hover:text-white">Instagram</a>
        </div>
      </div>

    </div>

    <div class="mt-8 border-t border-gray-700 pt-6 text-center text-sm text-gray-500">
      &copy; {{ new Date().getFullYear() }} {{ copyright }}
    </div>
  </footer>
</template>

<script setup>
const props = defineProps({
  aboutTitle: {
    type: String,
    default: 'About Us'
  },
  aboutText: {
    type: String,
    default:
      'We connect talented people with IT opportunities worldwide. Our mission is to empower learners to build successful tech careers.'
  },
  email: {
    type: String,
    default: 'support@myvueapp.com'
  },
  phone: {
    type: String,
    default: '+1 (555) 123-4567'
  },
  address: {
    type: String,
    default: '123 Tech Road, Silicon Valley'
  },
  facebook: {
    type: String,
    default: '#'
  },
  twitter: {
    type: String,
    default: '#'
  },
  linkedin: {
    type: String,
    default: '#'
  },
  instagram: {
    type: String,
    default: '#'
  },
  copyright: {
    type: String,
    default: 'MyVueApp. All rights reserved.'
  }
})
</script>
