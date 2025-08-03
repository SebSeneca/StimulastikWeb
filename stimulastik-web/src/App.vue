<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="app-layout">
    <nav class="navbar">
      <RouterLink to="/">Hjem</RouterLink>
      <RouterLink to="/about">Information</RouterLink>
      <img src="@/assets/logo.png" alt="Logo" class="navbar-logo" />
    </nav>
    <main class="main-content">
      <RouterView />
    </main>
    <footer class="footer">
      <span>© 2025 Stimulastik v. Karina Jensen</span>
      <span>
        Hjemmeside udviklet og vedligeholdt af
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
  height: 100vh;
}

.navbar {
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
  font-style: normal;
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
  display: flex;
  flex-direction: column;
  flex: 1 1 0;
  min-height: 0;
  overflow: auto;
  padding-bottom: 1rem; /* Optional: for spacing below content */
}
.footer {
  height: 48px;
  width: 100%;
  flex-shrink: 0;
  background: var(--stimulastik-tertiary);
  color: #fff;
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
</style>
