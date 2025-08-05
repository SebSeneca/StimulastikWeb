<template>
  <div class="base-view about-view">
    <h1 class="base-title" style="margin-bottom: 0">Om mig</h1>
    <InfoSection
      :imgSrc="photo"
      imgAlt="Karina Jensen"
      header="Mit navn er Karina Jensen"
      body="Jeg blev i 2020 uddannet ergoterapeut på UCL i Odense og i 2023 certificeret stimulastik instruktør. Jeg arbejder til dagligt som ergoterapeut på Slagelse sygehus og har ved siden af min hobbyvirksomhed med stimulastik. + mere tekst"
      :mirror="true"
    />
  </div>
</template>

<script setup lang="ts">
import InfoSection from '@/components/InfoSection.vue'
import photo from '@/assets/karina.jpg'
</script>

<style scoped>
.about-view .info-section {
  min-height: 500px;
}

@media (max-width: 600px) {
  .about-view :deep(.info-section-image) {
    height: 340px !important;
    min-height: 220px !important;
    max-height: 400px !important;
    width: 100% !important;
    object-fit: cover !important;
    display: block;
  }
}
</style>
