<template>
  <div class="base-view about-view">
    <h1 class="base-title" style="margin-bottom: 0">Om mig</h1>
    <InfoSection
      :imgSrc="photo"
      imgAlt="Karina Jensen"
      header="Mit navn er Karina Jensen"
      :body="infoTxt"
      :mirror="true"
      buttonText="Kontakt mig"
      @buttonClick="handleBookingClick"
    />
  </div>
</template>

<script setup lang="ts">
import InfoSection from '@/components/InfoSection.vue'
import { useRouter } from 'vue-router'
import photo from '@/assets/karina.jpg'

const infoTxt =
  'Jeg hedder Karina Jensen og er 31 år. Jeg arbejder til dagligt som ergoterapeut på Slagelse sygehus' +
  ' og har ved siden af denne hobby virksomhed med stimulastik.' +
  '<br><br>Jeg har altid haft en passion for børns sansemotoriske udvikling og da jeg i 2020 selv blev mor ' +
  'for første gang blev min nysgerrighed kun endnu større. Jeg har derfor efterfølgende nørdet ned i ' +
  'børns sanser, deres udvikling og særligt hvordan vi så kan stimulere dem.<br><br>' +
  'I 2023 blev jeg certificeret stimulastik instruktør og har efterfølgende haft en masse dejlige hold.'

const router = useRouter()

function handleBookingClick() {
  router.push('/booking')
}
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
