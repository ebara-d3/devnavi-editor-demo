<script setup lang="ts">
import { RouterLink, RouterView, useRoute } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'

const currentRoute = useRoute();
</script>

<template>
  <header class="header">
    <img alt="Vue logo" class="logo" src="@/assets/logo.png" height="125" />
  </header>
  <nav class="nav"> <ul>
      <li :class="currentRoute.name === 'home' ? 'selected' : ''" >
      <RouterLink to="/">Editor 1</RouterLink>
      </li>
      <li :class="currentRoute.name === 'editor2' ? 'selected' : ''" >
      <RouterLink to="/editor2">Editor 2</RouterLink>
      </li>
      <li :class="currentRoute.name === 'editor3' ? 'selected' : ''" >
      <RouterLink to="/editor3">Editor 3</RouterLink>
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
    .selected {
      font-weight: 700;
    }
  }
</style>
