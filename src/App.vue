<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <header>
    <nav>
      <RouterLink to="/">Home</RouterLink> |
      <RouterLink to="/meapp">MeApp</RouterLink>
    </nav>
  </header>

  <RouterView />
</template>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
nav {
  padding: 30px;
  text-align: center;
}
nav a {
  font-weight: bold;
  text-decoration: none;
  padding: 10px;
}
nav a.router-link-exact-active {
  color: #ffff;
  background: #155e75;
  border-radius: 10px;
}
</style>