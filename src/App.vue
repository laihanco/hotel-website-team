<script setup lang="ts">
import { RouterView } from 'vue-router';
import BaseNav from '@/components/layout/BaseNav.vue';
import BaseFooter from '@/components/layout/BaseFooter.vue';
</script>

<template>
  <BaseNav />

  <div class="p-10">
    <RouterView />
  </div>

  <BaseFooter />
</template>

<style></style>
