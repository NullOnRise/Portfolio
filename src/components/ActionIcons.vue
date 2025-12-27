<script setup>
const props = defineProps({
  isMuted: {
    type: Boolean,
    default: false,
  },
})

const emit = defineEmits(['open-github', 'handle-discord', 'copy-email', 'toggle-mute'])
</script>

<template>
  <div class="action-row">
    <button class="icon-btn" aria-label="Open GitHub" @click="emit('open-github')">
      <i class="ri-github-fill" aria-hidden="true"></i>
    </button>

    <button class="icon-btn" aria-label="Open or copy Discord" @click="emit('handle-discord')">
      <i class="ri-discord-fill" aria-hidden="true"></i>
    </button>

    <button class="icon-btn" aria-label="Copy email" @click="emit('copy-email')">
      <i class="ri-mail-fill" aria-hidden="true"></i>
    </button>

    <button class="icon-btn" :aria-label="isMuted ? 'Unmute audio' : 'Mute audio'" @click="emit('toggle-mute')">
      <i v-if="!isMuted" class="ri-volume-up-fill" aria-hidden="true"></i>
      <i v-else class="ri-volume-mute-fill" aria-hidden="true"></i>
    </button>
  </div>
</template>
