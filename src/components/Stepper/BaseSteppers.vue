<template>
  <ul class="flex items-center justify-center">
    <base-stepper
      v-for="(step, index) in steps"
      :key="index"
      :active="activeStep >= index + 1"
      :showSeparator="index + 1 !== steps.length"
      :indicator="index + 1"
      >{{ step }}
      <template v-slot:separator>
        <base-separator></base-separator>
      </template>
    </base-stepper>
  </ul>
</template>

<script setup lang="ts">
import { ref, watchEffect } from 'vue';
import type { Ref } from 'vue';
import BaseStepper from './BaseStepper.vue';
import BaseSeparator from './BaseSeparator.vue';

interface Props {
  activeStep?: number;
}

const props = withDefaults(defineProps<Props>(), {
  activeStep: 1,
});

const activeStep = ref(props.activeStep);

const steps: Ref<string[]> = ref(['輸入信箱及密碼', '填寫基本資料']);

watchEffect(() => {
  if (props.activeStep <= 0) {
    activeStep.value = 0;
    return;
  }
  if (props.activeStep >= steps.value.length) {
    activeStep.value = steps.value.length;
    return;
  }
  activeStep.value = props.activeStep;
  return;
});
</script>

<style scoped></style>
