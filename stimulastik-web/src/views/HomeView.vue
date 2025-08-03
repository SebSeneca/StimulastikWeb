<template>
  <div class="base-view">
    <h1 class="base-title">Stimulastik v. Karina Jensen</h1>
    <h2 class="home-subheader">
      Stimulastik er et ergoterapeutisk koncept, som handler om stimulation og gymnastik for
      spædbørn og deres forældre.
    </h2>
    <h2 class="home-subheader">
      Stimulastik foregår på små hold, hvor forældre er aktive sammen med deres børn.
    </h2>
    <ImageInfoCard :imgSrc="photo2" imgAlt="Lege og øvelser" @click="handleBookingClick">
      <p>Book en privat session</p>
    </ImageInfoCard>
    <ImageInfoCard :imgSrc="idalouLogo" imgAlt="Idalou" @click="handleIdalouClick">
      <p>Tilmeld dig til hold hos Idalou.</p>
    </ImageInfoCard>
    <ImageInfoCard :imgSrc="photo1" imgAlt="Kreativitet" @click="handleStimulastikClick">
      <p>Lær mere om fordelene ved stimulastik.</p>
    </ImageInfoCard>
  </div>
</template>

<script setup lang="ts">
import ImageInfoCard from '@/components/ImageInfoCard.vue'
import { useRouter } from 'vue-router'

// Import images using Vite's asset handling
import photo1 from '@/assets/photo1.jpg'
import photo2 from '@/assets/photo2.jpg'
import idalouLogo from '@/assets/Idalou.jpg'

const router = useRouter()

function handleBookingClick() {
  router.push('/booking')
}

function handleIdalouClick() {
  window.open('https://idalou.dk/hold/stimulastik/', '_blank')
}

function handleStimulastikClick() {
  router.push('/stimulastik')
}
</script>

<style scoped>
.home-subheader {
  font-size: 1.5rem;
  font-weight: 500;
  color: var(--stimulastik-secondary);
  text-align: center;
  margin-bottom: 1.5rem;
}

@media (max-width: 600px) {
  .home-subheader {
    font-size: 1.2rem;
    font-weight: 500;
    color: var(--stimulastik-secondary);
    text-align: center;
    margin-bottom: 1.5rem;
  }
}
</style>
