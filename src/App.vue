<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <header class="header">
    <img alt="Vue logo" class="logo" src="@/assets/logo.png" height="125" />
  </header>
  <nav class="nav">
    <ul>
      <li>
      <RouterLink to="/">Editor 1</RouterLink>
      </li>
      <li>
      <RouterLink to="/editor2">Editor 2</RouterLink>
      </li>
    </ul>
  </nav>

  <RouterView />
</template>

<style scoped>
  .header {
    display: flex;
    background: rgb(255, 255, 9);
    width: 100%;
  }
  .nav {
    padding: 1rem 2rem;
    border-bottom: 1px solid #ccc;
    ul {
      display: flex;
      gap: 1rem;
      * {
        text-decoration: underline;
        font-size: 1.2rem;
      }
    }
  }
</style>
