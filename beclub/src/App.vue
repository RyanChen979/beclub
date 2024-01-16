<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/contact">Contact</RouterLink>
        <a href="discord.gg/" target="_blank">Discord</a>
      </nav>
    </div>
  </header>

  <RouterView />

  <footer>footer</footer>
</template>

<style scoped>
header {
  line-height: 1.5;
  margin-bottom: 2rem;
}
footer {
  bottom: 0%;
  width: 100%;
}

nav {
  width: 100%;
  font-size: 20px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}
</style>
