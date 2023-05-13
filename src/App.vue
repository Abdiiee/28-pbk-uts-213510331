<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <header>
    <div class="navbar">
      <RouterLink to="/">Home</RouterLink> |
      <RouterLink to="/meapp">MeApp</RouterLink>
    </div>
  </header>

  <RouterView/>
</template>

<style scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.navbar {
  padding-top: 20px;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background-color: #cffafe;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.navbar a {
  font-weight: bold;
  text-decoration: none;
  padding: 10px;
}

.navbar a.router-link-exact-active {
  color: #ffff;
  background: #155e75;
  border-radius: 10px;
}</style>