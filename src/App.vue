<script setup lang="ts">
import { RouterView } from 'vue-router';
import BaseNav from '@/components/layout/BaseNav.vue';
</script>

<template>
  <BaseNav />

  <div class="p-10">
    <RouterView />
  </div>
</template>

<style></style>
