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
    <ImageInfoCard :imgSrc="photo1" imgAlt="Lege og øvelser" :mirrored="false">
      <p>Leg og bevægelse styrker barnets motorik og sociale færdigheder.</p>
    </ImageInfoCard>
    <ImageInfoCard :imgSrc="photo2" imgAlt="Sanseudvikling" :mirrored="true">
      <p>Sanselege hjælper børn med at udforske verden og udvikle nye kompetencer.</p>
    </ImageInfoCard>
    <ImageInfoCard :imgSrc="photo3" imgAlt="Kreativitet" :mirrored="false">
      <p>Kreative aktiviteter fremmer fantasi og problemløsning hos børn.</p>
    </ImageInfoCard>
  </div>
</template>

<script setup lang="ts">
import ImageInfoCard from '@/components/ImageInfoCard.vue'

// Import images using Vite's asset handling
import photo1 from '@/assets/photo1.jpg'
import photo2 from '@/assets/photo2.jpg'
import photo3 from '@/assets/photo3.jpg'
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
