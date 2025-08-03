<template>
  <div class="image-info-card" :class="{ mirrored }">
    <img :src="imgSrc" :alt="imgAlt" class="image-info-card__image" />
    <InfoCard style="height: 120px; background-color: var(--stimulastik-tertiary)">
      <slot />
    </InfoCard>
  </div>
</template>

<script setup lang="ts">
import InfoCard from './InfoCard.vue'

defineProps<{
  imgSrc: string
  imgAlt: string
  mirrored: boolean
}>()
</script>

<style scoped>
.image-info-card {
  display: flex;
  flex-direction: row;
  align-items: center;
  background-color: var(--stimulastik-primary);
  gap: 2rem;
  padding: 2rem 1.5rem;
  width: 100%;
  max-width: 900px;
  margin-bottom: 2rem;
  border: 2px solid var(--stimulastik-tertiary, #6c9568);
  border-radius: 1.5rem;
  transition:
    box-shadow 0.2s,
    border-color 0.2s;
  box-shadow: 0 2px 8px rgba(44, 64, 45, 0.06);
}

.image-info-card.mirrored {
  flex-direction: row-reverse;
}

.image-info-card:hover {
  box-shadow: 0 6px 24px rgba(44, 64, 45, 0.18);
  border-color: var(--stimulastik-secondary, #2e402d);
}

.image-info-card__image {
  flex: 0 1 65%;
  width: 65%;
  max-width: 520px;
  border-radius: 1rem;
  border: 0.5px solid var(--stimulastik-tertiary);
  object-fit: cover;
  display: block;
}

.image-info-card > :deep(.info-card) {
  flex: 0 1 35%;
  width: 35%;
  min-width: 180px;
  max-width: 320px;
  padding: 2rem 1rem;
}
</style>
