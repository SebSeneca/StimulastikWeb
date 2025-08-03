<template>
  <div class="home">
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
.home {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
  width: 100%;
  height: 100%;
  padding-top: 3rem;
}

.home-title {
  font-size: 2.2rem;
  font-weight: 700;
  margin-bottom: 2rem;
  color: var(--stimulastik-secondary);
  letter-spacing: -1px;
  text-align: center;
}
</style>
