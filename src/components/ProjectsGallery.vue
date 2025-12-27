<script setup>
const props = defineProps({
  projects: {
    type: Array,
    required: true,
  },
})
</script>

<template>
  <section class="projects">
    <div class="section-header">
      <h2>Projects</h2>
      <p class="muted">Selected works and experiments.</p>
    </div>
    <div class="project-grid">
      <a
        v-for="project in projects"
        :key="project.title"
        class="project-card glass"
        :href="project.url"
        target="_blank"
        rel="noopener"
      >
        <div class="project-img">
          <img :src="project.imageUrl" :alt="project.title" loading="lazy" />
          <div class="img-overlay"></div>
        </div>
        <div class="project-body">
          <div class="project-title-row">
            <h3>{{ project.title }}</h3>
            <span class="arrow">↗</span>
          </div>
          <p class="project-desc">{{ project.description }}</p>
          <div v-if="project.tags?.length" class="tag-row">
            <span v-for="tag in project.tags" :key="tag" class="tag">{{ tag }}</span>
          </div>
        </div>
      </a>
    </div>
  </section>
</template>
