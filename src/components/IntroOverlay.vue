<script setup>
const emit = defineEmits(['proceed'])
</script>

<template>
  <div
    class="intro-overlay"
    @click="emit('proceed')"
    role="button"
    tabindex="0"
    @keydown.enter.prevent="emit('proceed')"
    @keydown.space.prevent="emit('proceed')"
  >
    <div class="intro-card">
      <p>Click to continue...</p>
    </div>
  </div>
</template>
