<script setup>
import { RouterLink, RouterView } from "vue-router";

let prevScrollpos = window.scrollY;
window.onscroll = function () {
  var currentScrollPos = window.scrollY;
  if (prevScrollpos > currentScrollPos) {
    document.getElementById("wrapper").style.top = "0";
  } else {
    document.getElementById("wrapper").style.top = "-5rem";
  }
  prevScrollpos = currentScrollPos;
};
</script>

<template>
  <header>
    <div id="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/contact">Contact</RouterLink>
        <a href="https://discord.gg/xKyJ8KzwBN" target="_blank">Discord</a>
      </nav>
    </div>
  </header>

  <RouterView class="content" />

  <footer>footer</footer>
</template>

<style scoped>
#wrapper {
  width: 100%;
  padding: 1rem;

  position: fixed;
  z-index: 1;
  transition: top 0.5s;
  border-bottom: 1px solid;
  background-color: white;
}

.content {
  padding-top: 8rem;
  position: relative;
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

footer {
  bottom: 0%;
  width: 100%;
}
</style>
