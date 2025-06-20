
<template>
  <nav class="space-x-4 mt-2 md:mt-0">
    <RouterLink
      to="/"
      class="hover:bg-blue-800 px-3 py-2 rounded transition"
      active-class="bg-blue-900"
      exact
    >
      Home
    </RouterLink>
    <RouterLink
      to="/about"
      class="hover:bg-blue-800 px-3 py-2 rounded transition"
      active-class="bg-blue-900"
    >
      About Us
    </RouterLink>
    <RouterLink
      to="/contact"
      class="hover:bg-blue-800 px-3 py-2 rounded transition"
      active-class="bg-blue-900"
    >
      Contact
    </RouterLink>
    <RouterLink
      to="/user"
      class="hover:bg-blue-800 px-3 py-2 rounded transition"
      active-class="bg-blue-900"
    >
      User List
    </RouterLink>
  </nav>
</template>
<script setup>
import { RouterLink } from 'vue-router'

defineProps({
  links: {
    type: Array,
    default: () => [
      { to: '/', label: 'Home', exact: true },
      { to: '/about', label: 'About Us' },
      { to: '/contact', label: 'Contact' },
      { to: '/user', label: 'User List' }
    ]
  },
  activeClass: {
    type: String,
    default: 'bg-blue-900'
  },
  hoverClass: {
    type: String,
    default: 'hover:bg-blue-800'
  }
})
</script>