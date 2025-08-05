<template>
  <div class="base-view" style="padding-left: 1rem; padding-right: 1rem; padding-bottom: 1rem">
    <h1 class="base-title">Book private sessioner</h1>
    <p class="info-text">
      Kunne i tænke jer at booke en stimulastik session til jeres næste mødregruppe? Eller har I et
      ønske om at få en privat session i jeres eget hjem?
    </p>
    <p class="info-text">
      Tag kontakt og så aftaler vi sammen hvor mange sessioner forløbet skal bestå af samt hvor og
      hvornår sessionerne vil finde sted.
    </p>
    <p class="info-text">
      Et typisk forløb består af 6 sessioner, som finder sted hver eller hveranden uge. Det vil være
      tirsdag eftermiddag eller i weekenderne i et af jeres hjem. Der skal være 3-7 babyer i gruppen
      i alderen 2-12 måneder.
    </p>
    <p class="info-text">Prisen tilpasses antallet af babyer og hvor sessionerne finder sted.</p>
    <p class="info-text">
      Skriv til mig for at høre mere. Jeg glæder mig til at høre fra jer og lege med jer og jeres
      babyer!
    </p>
    <form class="booking-form" @submit.prevent="handleSubmit">
      <label>
        Navn:
        <input v-model="name" type="text" required placeholder="Dit navn" />
      </label>
      <label>
        Emne:
        <input v-model="subject" type="text" required placeholder="Emne for din henvendelse" />
      </label>
      <label>
        E-mail:
        <input v-model="email" type="email" required placeholder="Din e-mail" />
      </label>
      <label>
        Besked:
        <textarea v-model="body" required placeholder="Skriv din besked her..." rows="5"></textarea>
      </label>
      <div v-if="error" class="error-message">{{ error }}</div>
      <button type="submit">Send forespørgsel</button>
    </form>
    <div v-if="success" class="success-message">
      Din besked er sendt! Tak for din henvendelse. Vi vender tilbage til dig hurtigst muligt.
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import emailjs from 'emailjs-com'

type EmailParams = {
  name: string
  subject: string
  email: string
  message: string
}

const name = ref('')
const subject = ref('')
const email = ref('')
const body = ref('')
const success = ref(false)
const error = ref('')

const SERVICE_ID = 'service_sioey0h'
const TEMPLATE_ID = 'template_ff9v8sj'
const USER_ID = 'LUPrxoOLu4_T4EcTT' // public key

function handleSubmit() {
  error.value = ''
  name.value = name.value.trim()
  subject.value = subject.value.trim()
  email.value = email.value.trim()
  body.value = body.value.trim()

  if (!name.value) {
    error.value = 'Du skal angive dit navn.'
    return
  }
  if (!email.value) {
    error.value = 'Du skal angive en e-mailadresse.'
    return
  }

  const templateParams: EmailParams = {
    name: name.value,
    subject: subject.value,
    email: email.value,
    message: body.value,
  }

  emailjs.send(SERVICE_ID, TEMPLATE_ID, templateParams, USER_ID).then(
    () => {
      success.value = true
      // Optionally reset form fields
      name.value = ''
      subject.value = ''
      email.value = ''
      body.value = ''
    },
    (err) => {
      error.value = 'Der opstod en fejl ved afsendelse. Prøv igen senere.'
      console.error(err)
    },
  )
}
</script>

<style scoped>
.info-text {
  margin-bottom: 1.5rem;
  font-size: 1.1rem;
  text-align: center;
  color: var(--stimulastik-secondary);
}

.booking-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
  width: 100%;
  max-width: 400px;
  margin: 0 auto;
}

.booking-form label {
  display: flex;
  flex-direction: column;
  font-weight: 500;
  color: var(--stimulastik-secondary);
}

.booking-form input,
.booking-form textarea {
  margin-top: 0.5rem;
  padding: 0.5rem;
  border: 1px solid var(--stimulastik-tertiary);
  border-radius: 0.5rem;
  font-size: 1rem;
  font-family: inherit;
}

.booking-form button {
  margin-top: 1rem;
  padding: 0.7rem;
  background: var(--stimulastik-tertiary);
  color: #fff;
  border: none;
  border-radius: 0.5rem;
  font-size: 1.1rem;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.2s;
}

.booking-form button:hover {
  background: var(--stimulastik-secondary);
}

.success-message {
  margin-top: 1.5rem;
  color: green;
  font-weight: 600;
  text-align: center;
}

.error-message {
  color: #b00020;
  font-weight: 600;
  margin-bottom: 0.5rem;
  text-align: center;
}
</style>
