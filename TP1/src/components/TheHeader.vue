<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <header>
    <nav>
      <div class="logo">
        <a href="/">MonSite</a>
      </div>

      <ul class="nav-links" :class="{ open: isMenuOpen }">
        <li><a href="/">Accueil</a></li>
        <li><a href="/about">À propos</a></li>
        <li><a href="/contact">Contact</a></li>
      </ul>

      <button class="burger" @click="toggleMenu">
        ☰
      </button>
    </nav>
  </header>
</template>

<style scoped>
header {
  background: #fff;
  border-bottom: 1px solid #eee;
  padding: 0 2rem;
}

nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 60px;
}

.logo a {
  font-weight: 600;
  font-size: 1.2rem;
  text-decoration: none;
  color: inherit;
}

.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
  margin: 0;
  padding: 0;
}

.nav-links a {
  text-decoration: none;
  color: inherit;
  font-size: 0.95rem;
}

.nav-links a:hover {
  opacity: 0.6;
}

.burger {
  display: none;
  background: none;
  border: none;
  font-size: 1.5rem;
  cursor: pointer;
}

@media (max-width: 768px) {
  .burger {
    display: block;
  }

  .nav-links {
    display: none;
    position: absolute;
    top: 60px;
    left: 0;
    right: 0;
    background: #fff;
    flex-direction: column;
    padding: 1rem 2rem;
    border-bottom: 1px solid #eee;
  }

  .nav-links.open {
    display: flex;
  }
}
</style>