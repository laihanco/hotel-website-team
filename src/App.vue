<script setup lang="ts">
import { RouterView } from 'vue-router';
</script>

<template>
  <nav class="p-5 text-center">
    <router-link to="/" class="text-white mr-4">Color Palette</router-link>
    <router-link to="/about" class="text-white mr-4">Typography</router-link>
    <router-link to="/component-view" class="text-white">Component</router-link>
  </nav>

  <div class="p-10">
    <RouterView />
  </div>
</template>

<style></style>
