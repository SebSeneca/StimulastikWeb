<template>
  <div class="base-view">
    <h1 class="base-title">Hvad er stimulastik?</h1>
    <div class="info-card-row">
      <InfoCard>
        <p>
          Stimulastik er et ergoterapeutisk koncept, der fokuserer på at støtte spædbørns udvikling
          gennem leg og bevægelse.
        </p>
      </InfoCard>
      <InfoCard>
        <p>
          Det involverer aktiviteter, der fremmer motoriske færdigheder, sanseoplevelser og social
          interaktion.
        </p>
      </InfoCard>
    </div>
  </div>
</template>

<script setup lang="ts">
import InfoCard from '@/components/InfoCard.vue'
</script>

<style scoped>
.info-card-row {
  display: flex;
  gap: 2rem;
  justify-content: center;
  align-items: flex-start;
  flex-wrap: wrap;
}
</style>
