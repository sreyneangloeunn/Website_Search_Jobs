<template>
  <div class="bg-white rounded-lg overflow-hidden shadow-md hover:shadow-lg transition">
    <img :src="image" alt="Card Image" class="w-full h-48 object-cover" v-if="image" />
    <div class="p-5">
      <h3 class="text-xl font-semibold mb-2">{{ title }}</h3>
      <p class="text-gray-600 mb-4">{{ content }}</p>
      <slot name="footer"></slot>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  content: String,
  image: String
})
</script>
