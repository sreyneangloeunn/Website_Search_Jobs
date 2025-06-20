<script setup>
import Navbar from './components/global/layout/Navbar.vue';
import { RouterView } from 'vue-router'
</script>
<template>
  <header class="bg-blue-700 text-white shadow-md">
    <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between p-4">

      <!-- Logo or Greeting -->
      <div class="text-xl font-semibold">
        JobSearch
      </div>

      <!-- Use Navbar component -->
      <Navbar />
    </div>
  </header>

  <main class="p-6">
    <RouterView />
  </main>
</template>

<style scoped>

/* No additional scoped CSS needed with Tailwind */
</style>
