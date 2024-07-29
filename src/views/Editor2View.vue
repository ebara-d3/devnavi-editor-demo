<script setup lang="ts">
import {ref} from "vue";

const text = ref('# Hello, Markdown editor! \n $$\\sum_{i=1}^n a_i=0$$')
</script>

<template>
  <main class="main">
    <h1>Markdownエディタ</h1>
    <v-md-editor v-model="text" height="400px"></v-md-editor>
  </main>
</template>

<style scoped>
.main {
  padding: 2rem 3rem;
}
</style>
