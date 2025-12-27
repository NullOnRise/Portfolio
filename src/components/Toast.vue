<script setup>
const props = defineProps({
  toast: {
    type: Object,
    required: true,
  },
})
</script>

<template>
  <transition name="fade">
    <div v-if="toast.visible" class="toast glass" role="status" aria-live="polite">
      {{ toast.message }}
    </div>
  </transition>
</template>
