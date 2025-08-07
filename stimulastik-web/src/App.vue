<script setup lang="ts">
import { RouterLink, RouterView, useRoute } from 'vue-router'
import { ref, watch } from 'vue'
// QR CODE generated from https://www.qrcode-monkey.com/#
const route = useRoute()
const transitionName = ref('fade')
const logoAnimated = ref(false)

// Watch for route changes
watch(
  () => route.path,
  (to, from) => {
    if (to === from) return

    // Home
    if (to === '/') {
      transitionName.value = 'slide-left'
    } else if (from === '/') {
      transitionName.value = 'slide-right'
    }

    // About
    if (to === '/about') {
      transitionName.value = 'slide-right'
    } else if (from === '/about') {
      transitionName.value = 'slide-left'
    }

    // Stimulastik
    if (to === '/stimulastik' && from === '/') {
      transitionName.value = 'slide-right'
    } else if (to === '/stimulastik' && from === '/about') {
      transitionName.value = 'slide-left'
    } else if (from === '/stimulastik' && to === '/about') {
      transitionName.value = 'slide-right'
    } else if (from === '/stimulastik' && to === '/') {
      transitionName.value = 'slide-left'
    }
  },
)

function animateLogo() {
  void document.getElementById('navbar-logo')?.offsetWidth
  logoAnimated.value = true
}

function handleLogoAnimationEnd() {
  logoAnimated.value = false
}
</script>

<template>
  <div class="app-layout">
    <nav class="navbar">
      <RouterLink to="/">Hjem</RouterLink>
      <RouterLink to="/stimulastik">Om stimulastik</RouterLink>
      <RouterLink to="/about">Om mig</RouterLink>
      <img
        src="@/assets/logo.png"
        alt="Logo"
        class="navbar-logo"
        :class="{ 'animate__animated animate__hinge': logoAnimated }"
        @click="animateLogo"
        @animationend="handleLogoAnimationEnd"
      />
    </nav>
    <main class="main-content">
      <RouterView v-slot="{ Component }">
        <Transition :name="transitionName" mode="out-in">
          <Component :is="Component" />
        </Transition>
      </RouterView>
    </main>
    <footer class="footer">
      <span>© 2025 Stimulastik v. Karina Jensen</span>
      <span>
        Hjemmeside udviklet af
        <a
          href="https://www.linkedin.com/in/sebastian-hansen-2303051a1/"
          target="_blank"
          rel="noopener"
          class="linkedin-link"
        >
          Sebastian Hansen
        </a>
      </span>
    </footer>
  </div>
</template>

<style scoped>
.app-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* Slide Left */
.slide-left-enter-active,
.slide-left-leave-active {
  transition:
    transform 0.2s cubic-bezier(0.55, 0, 0.1, 1),
    opacity 0.2s;
}
.slide-left-enter-from {
  transform: translateX(-100%);
  opacity: 0;
}
.slide-left-leave-to {
  transform: translateX(100%);
  opacity: 0;
}

/* Slide Right */
.slide-right-enter-active,
.slide-right-leave-active {
  transition:
    transform 0.2s cubic-bezier(0.55, 0, 0.1, 1),
    opacity 0.2s;
}
.slide-right-enter-from {
  transform: translateX(100%);
  opacity: 0;
}
.slide-right-leave-to {
  transform: translateX(-100%);
  opacity: 0;
}

.navbar {
  position: sticky;
  top: 0;
  z-index: 100;
  border-bottom: 1px solid var(--stimulastik-secondary);
  height: 55px;
  flex-shrink: 0;
  background: var(--stimulastik-primary);
  color: #fff;
  display: flex;
  align-items: center;
  padding: 0 2rem;
}

.navbar a {
  color: var(--color-text);
  text-decoration: none;
  margin-right: 2rem;
  font-size: 1rem;
  font-weight: 500;
  border-radius: 0.5rem;
  padding: 0.5rem 1rem;
  transition:
    box-shadow 0.2s,
    background 0.2s,
    color 0.2s;
}

.navbar a:hover {
  background: var(--stimulastik-tertiary);
  color: var(--color-white);
  box-shadow: 0 2px 12px 0 rgba(108, 149, 104, 0.15);
  text-decoration: none;
}

.navbar a.router-link-exact-active {
  color: var(--color-white);
  background: var(--stimulastik-secondary);
  box-shadow: 0 2px 12px 0 rgba(108, 149, 104, 0.15);
}

.navbar-logo {
  margin-left: auto;
  height: 40px;
  width: auto;
  display: block;
}

.main-content {
  flex: 1 0 auto;
  padding-bottom: 1rem;
  overflow: hidden;
}

.footer {
  flex-shrink: 0;
  height: 48px;
  width: 100%;
  background: var(--stimulastik-primary);
  border-top: 1px solid var(--stimulastik-secondary);
  color: var(--color-text);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 2rem;
  font-size: 0.95rem;
  font-style: italic;
  letter-spacing: 0.5px;
}

.linkedin-link {
  color: inherit;
  text-decoration: underline;
}
.linkedin-link:hover {
  color: #0a66c2;
}

/* --- MOBILE RESPONSIVE STYLES --- */
@media (max-width: 600px) {
  .navbar {
    flex-direction: row;
    height: auto;
    padding: 0.5rem 1rem;
    gap: 0.5rem;
  }
  .navbar a {
    margin-right: 0;
    font-size: 0.9rem;
    padding: 0.5rem 0.8rem;
  }
  .navbar-logo {
    height: 28px;
  }
  .main-content {
    padding-bottom: 0.5rem;
  }
  .footer {
    flex-direction: column;
    height: auto;
    padding: 0.5rem 1rem;
    font-size: 0.9rem;
    gap: 0.3rem;
    text-align: center;
  }
  .slide-left-enter-active,
  .slide-left-leave-active,
  .slide-right-enter-active,
  .slide-right-leave-active {
    transition:
      transform 0.09s cubic-bezier(0.55, 0, 0.1, 1),
      opacity 0.09s;
  }
}
</style>
