<template>
  <div class="base-view">
    <h1 class="home-title">Stimulastik v. Karina Jensen</h1>
    <InfoCard>
      <p>
        Udforsk hvordan du kan stimulere dit barn igennem en række lege og øvelser, som nemt kan
        udføres derhjemme
      </p>
    </InfoCard>
  </div>
</template>

<script setup lang="ts">
import InfoCard from '@/components/InfoCard.vue'
</script>

<style scoped>
.home-title {
  font-size: 2.2rem;
  font-weight: 700;
  margin-bottom: 2rem;
  color: var(--stimulastik-secondary);
  letter-spacing: -1px;
  text-align: center;
}
</style>
