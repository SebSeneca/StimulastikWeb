<template>
  <section class="info-section">
    <img :src="imgSrc" :alt="imgAlt" class="info-section-image" />
    <div class="info-section-content">
      <h2 class="info-section-header">{{ header }}</h2>
      <div class="info-section-body-wrapper">
        <p class="info-section-body">{{ body }}</p>
      </div>
      <button class="info-section-button" @click="$emit('buttonClick')">
        {{ buttonText }}
      </button>
    </div>
  </section>
</template>

<script setup lang="ts">
defineEmits(['buttonClick'])

defineProps<{
  imgSrc: string
  imgAlt: string
  header: string
  body: string
  buttonText: string
}>()
</script>

<style scoped>
.info-section {
  display: flex;
  align-items: stretch;
  width: 100%;
  min-height: 280px;
  height: 360px;
  margin: 2.5rem 0;
  overflow: hidden;
}

.info-section-image {
  width: 50%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.info-section-content {
  flex: 1 1 50%;
  padding: 2.2rem 2rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  color: var(--stimulastik-secondary);
  background: var(--stimulastik-primary);
}

.info-section-header {
  font-size: 1.7rem;
  margin-bottom: 0.7rem;
  color: var(--stimulastik-secondary);
  font-family: Gabriola, serif;
}

.info-section-body-wrapper {
  background: var(--stimulastik-primary);
  padding: 1.1rem 1.3rem;
}

.info-section-body {
  font-size: 1rem;
  margin: 0;
  color: var(--stimulastik-secondary);
}

.info-section-button {
  align-self: flex-end;
  background: var(--stimulastik-tertiary);
  color: #fff;
  border: none;
  padding: 0.6rem 1.4rem;
  margin-top: 1rem;
  font-size: 1rem;
  font-weight: 350;
  font-family: 'Segoe UI', Inter, Arial, sans-serif;
  cursor: pointer;
  transition: background 0.2s;
}
.info-section-button:hover {
  background: var(--stimulastik-secondary);
}

@media (max-width: 900px) {
  .info-section {
    flex-direction: column;
    min-height: 0;
    max-height: none;
    height: auto;
  }
  .info-section-image {
    width: 100%;
    height: 180px;
  }
  .info-section-content {
    padding: 1.2rem 1rem;
  }
}
</style>
