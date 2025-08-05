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
  text-align: center;
  max-width: 420px;
  width: 100%;
  max-height: 350px;
  height: 100%;
  overflow: hidden;
}
</style>
