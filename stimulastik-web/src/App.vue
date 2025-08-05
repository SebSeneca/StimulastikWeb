<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="app-layout">
    <nav class="navbar">
      <RouterLink to="/">Hjem</RouterLink>
      <RouterLink to="/stimulastik">Om stimulastik</RouterLink>
      <RouterLink to="/about">Om mig</RouterLink>
      <img src="@/assets/logo.png" alt="Logo" class="navbar-logo" />
    </nav>
    <main class="main-content">
      <RouterView />
    </main>
    <footer class="footer">
      <span>© 2024 Stimulastik v. Karina Jensen</span>
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

.navbar {
  position: sticky;
  top: 0;
  z-index: 100;
  border-bottom: 1px solid var(--stimulastik-secondary);
  height: 60px;
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

.navbar a.router-link-exact-active {
  color: var(--color-white);
  background: var(--stimulastik-tertiary);
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
  overflow: auto;
  padding-bottom: 1rem;
}

.footer {
  flex-shrink: 0;
  height: 48px;
  width: 100%;
  background: var(--stimulastik-primary);
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
    margin-bottom: 0.5rem;
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
}
</style>
