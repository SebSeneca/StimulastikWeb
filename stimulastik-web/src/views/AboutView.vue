<template>
  <div class="base-view">
    <h1 class="base-title">Om mig</h1>
    <img :src="photo" alt="Karina Jensen" class="about-photo" />
    <div class="info-card-row">
      <InfoCard>
        <p>
          Jeg er en erfaren ergoterapeut med certificering i børns udvikling og læring gennem
          stimulastik.
        </p>
      </InfoCard>
      <InfoCard>
        <p>
          Jeg har arbejdet med stimulastik i samarbejde med lokale virksomheder og har en passion
          for at stimulere børns nysgerrighed og kreativitet gennem leg og læring.
        </p>
      </InfoCard>
    </div>
  </div>
</template>

<script setup lang="ts">
import InfoCard from '@/components/InfoCard.vue'
import photo from '@/assets/karina.jpg'
</script>

<style scoped>
.about-photo {
  display: block;
  margin: 2rem auto 2rem auto;
  max-width: 320px;
  width: 100%;
  height: auto;
  border-radius: 5.5rem;
  box-shadow: 0 2px 12px rgba(44, 64, 45, 0.1);
  object-fit: cover;
}

.info-card-row {
  display: flex;
  gap: 2rem;
  justify-content: center;
  align-items: flex-start;
  flex-wrap: wrap;
}

@media (max-width: 600px) {
  .about-photo {
    max-width: 200px;
    margin: 1.2rem auto 1.2rem auto;
    border-radius: 3rem;
  }
  .info-card-row {
    flex-direction: column;
    gap: 1rem;
    align-items: center;
  }
}
</style>
