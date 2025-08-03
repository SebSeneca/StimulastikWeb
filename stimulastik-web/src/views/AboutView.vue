<template>
  <div class="base-view">
    <h1>Information</h1>
    <div class="info-card-row">
      <InfoCard>
        <p>
          Karina Jensen er en erfaren ergoterapeut med certificering i børns udvikling og læring
          gennem stimulastik.
        </p>
      </InfoCard>
      <InfoCard>
        <p>
          Hun har arbejdet med stimulastik i samarbejde med lokale virksomheder og har en passion
          for at stimulere børns nysgerrighed og kreativitet gennem leg og læring.
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
