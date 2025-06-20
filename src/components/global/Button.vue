<template>
  <button
    :class="[
      'px-6 py-2 rounded-lg font-semibold transition duration-200',
      variantClass,
    ]"
    @click="$emit('click')"
  >
    <slot>Click Me</slot>
  </button>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  variant: {
    type: String,
    default: 'primary', // options: primary, secondary, danger, etc.
  },
})

const variantClass = computed(() => {
  switch (props.variant) {
    case 'secondary':
      return 'bg-gray-200 text-gray-800 hover:bg-gray-300'
    case 'danger':
      return 'bg-red-600 text-white hover:bg-red-700'
    default:
      return 'bg-blue-600 text-white hover:bg-blue-700'
  }
})
</script>
