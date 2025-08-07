<template>
  <div class="base-view">
    <h1 class="base-title animate__animated animate__fadeInDown" style="animation-duration: 0.7s">
      Hvad er stimulastik?
    </h1>
    <h2 class="base-subheader">
      Læs lidt om stimulastik og hvad det kan gøre for dig og dit barn.
    </h2>
    <InfoSection
      style="animation-delay: 0.1s; animation-duration: 0.5s"
      :imgSrc="photo3"
      imgAlt="Baby der leger"
      header="Ergoterapi"
      body="Stimulastik er et ergoterapeutisk koncept, som handler om stimulation og gymnastik for spædbørn og deres forældre. Stimulastik foregår på små hold, hvor forældre er aktive sammen med deres børn."
    />
    <InfoSection
      style="animation-delay: 0.2s; animation-duration: 0.5s"
      :imgSrc="photo4"
      imgAlt="Barn med legetøj"
      header="Inspiration"
      body="Vi skal sammen lave en række sjove lege og øvelser, som er ideer og inspiration til hvad I kan lave derhjemme sammen med jeres baby. Nogle lege kræver redskaber, mens andre nemt kan udføres uden. Jeg vil også have forberedt taktile sansemæssige oplevelser, hvor børnene f.eks. skal røre ved sansemåtter, slim eller sand. "
      :mirror="true"
    />
    <InfoSection
      style="animation-delay: 0.3s"
      :imgSrc="photo5"
      imgAlt="Mor med barn"
      header="Udvikling"
      body="Jeg vil på holdene benytte min ergoterapeutiske viden til at guide jer forældre til at stimulere børnenes basale sanser inden for deres nuværende og næste udviklingszone. Dette er med til at styrke børnene sansemotorisk, fremme deres udvikling og give dem bevægelsesglæde."
    />
  </div>
</template>

<script setup lang="ts">
import InfoSection from '@/components/InfoSection.vue'
import photo3 from '@/assets/photo3.jpg'
import photo4 from '@/assets/photo4.jpg'
import photo5 from '@/assets/photo5.jpg'
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
