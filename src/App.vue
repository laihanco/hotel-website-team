<script setup lang="ts">
import { RouterView } from 'vue-router';
import BaseNav from '@/components/layout/BaseNav.vue';
import BaseFooter from '@/components/layout/BaseFooter.vue';
import BaseModal from '@/components/BaseModal.vue';
</script>

<template>
  <div>
    <BaseNav />

    <main class="p-10">
      <RouterView />
    </main>

    <BaseFooter />
  </div>
</template>

<style></style>
