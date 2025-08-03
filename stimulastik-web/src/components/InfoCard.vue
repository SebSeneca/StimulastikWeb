<script setup lang="ts"></script>

<template>
  <div class="info-card">
    <slot />
  </div>
</template>

<style scoped>
.info-card {
  background: var(--stimulastik-primary);
  padding: 3rem 2.5rem;
  border-radius: 1.5rem;
  box-shadow: 0 8px 32px rgba(60, 72, 100, 0.15);
  text-align: center;
  max-width: 420px;
  width: 100%;
}
</style>
