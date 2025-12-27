<script setup>
const props = defineProps({
  profile: {
    type: Object,
    required: true,
  },
})
</script>

<template>
  <section class="profile">
    <div class="glass card main-card">
      <div class="shine"></div>
      <img :src="profile.avatarUrl" alt="Avatar de NullOnRise" class="avatar" />
      <h1>{{ profile.name }}</h1>
      <p class="subtitle">{{ profile.subtitle }}</p>

      <div class="location" aria-label="Ubicación">
        <svg width="18" height="18" viewBox="0 0 24 24" aria-hidden="true">
          <path
            fill="currentColor"
            d="M12 2a7 7 0 0 0-7 7c0 5.25 7 13 7 13s7-7.75 7-13a7 7 0 0 0-7-7Zm0 9.5a2.5 2.5 0 1 1 0-5a2.5 2.5 0 0 1 0 5Z"
          />
        </svg>
        <span>{{ profile.location }}</span>
      </div>

      <div class="chips">
        <span v-for="skill in profile.skills" :key="skill" class="chip">{{ skill }}</span>
      </div>
    </div>

    <div class="glass card mini-card" aria-label="Estado de NullOnRise">
      <img :src="profile.avatarUrl" alt="Avatar pequeño" class="mini-avatar" />
      <div class="mini-info">
        <div class="row">
          <strong>{{ profile.handle }}</strong>
          <span class="pill">Available</span>
        </div>
        <small>{{ profile.status }}</small>
      </div>
      <div class="mini-badges" aria-hidden="true">
        <span class="dot dot-blue"></span>
        <span class="dot dot-green"></span>
        <span class="dot dot-pink"></span>
      </div>
    </div>
  </section>
</template>
