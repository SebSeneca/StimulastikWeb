<template>
  <div class="base-view" style="padding-left: 0; padding-right: 0">
    <h1 class="base-title">Stimulastik v. Karina Jensen</h1>
    <h2 class="home-subheader">
      Stimulastik er et ergoterapeutisk koncept, som handler om stimulation og gymnastik for
      spædbørn og deres forældre.
    </h2>
    <h2 class="home-subheader">
      Stimulastik foregår på små hold, hvor forældre er aktive sammen med deres børn.
    </h2>
    <InfoSection
      :imgSrc="photo2"
      imgAlt="Lege og øvelser"
      header="Book en privat session"
      body="Ved booking af en privat session får du og din mødregruppe mulighed for et special tilpasset forløb, som opfylder jeres behov og ønsker inden for børnenes nærmeste udviklingszone. "
      buttonText="Kontakt mig for booking"
      @buttonClick="handleBookingClick"
    />
    <InfoSection
      :imgSrc="idalouLogo"
      imgAlt="Idalou"
      header="Tilmeld dig til hold hos Idalou"
      body="Kom ned til Idalous familieunivers og deltag i mit stimulastik hold. Tilmelding og kalender findes på Idalous hjemmeside."
      buttonText="Tilmeld"
      :mirror="true"
      @buttonClick="handleIdalouClick"
    />
    <InfoSection
      :imgSrc="photo1"
      imgAlt="Kreativitet"
      header="Lær mere om fordelene ved stimulastik"
      body="Kreative aktiviteter fremmer fantasi og problemløsning hos børn."
      buttonText="Læs mere"
      @buttonClick="handleStimulastikClick"
    />
  </div>
</template>

<script setup lang="ts">
import InfoSection from '@/components/InfoSection.vue'
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
