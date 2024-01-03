<template>
  <ul class="flex items-center justify-center">
    <BaseStepper :active="activeStep >= 1">
      輸入信箱及密碼
      <template v-slot:separator>
        <BaseSeparator></BaseSeparator>
      </template>
    </BaseStepper>
    <BaseStepper :active="activeStep >= 2">填寫基本資料</BaseStepper>
  </ul>
</template>

<script setup lang="ts">
import { toRefs } from 'vue';
import BaseStepper from './BaseStepper.vue';
import BaseSeparator from './BaseSeparator.vue';

interface Props {
  activeStep?: number;
}

const props = withDefaults(defineProps<Props>(), {
  activeStep: 1,
});

const { activeStep } = toRefs(props);
</script>

<style scoped></style>
