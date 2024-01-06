<template>
  <div>
    <h4>Stepper</h4>
    <div class="bg-neutral-black p-2 text-center">
      <base-steppers
        class="w-full max-w-[416px]"
        :activeStep="activeStep"
        :steps="['title', 'title', 'title']"
      ></base-steppers>
    </div>
    <button
      type="button"
      class="text-sm text-gray-900 bg-white ring-gray-300 hover:bg-gray-50 inline-flex items-center rounded-md px-3 py-2 font-semibold shadow-sm ring-1 ring-inset"
      @click="activeStep += 1"
    >
      increment</button
    ><button
      type="button"
      class="text-sm text-gray-900 bg-white ring-gray-300 hover:bg-gray-50 inline-flex items-center rounded-md px-3 py-2 font-semibold shadow-sm ring-1 ring-inset"
      @click="activeStep -= 1"
    >
      decrement
    </button>
    <h4>SectionTab</h4>
    <div class="bg-neutral-black p-2 text-center">
      <section-tab :tabs="tabs" v-model:value="tab">
        <template #oasis>
          <span class="text-neutral-white">oasis</span>
        </template>
        <template #theBeatles>
          <span class="text-neutral-white">the Beatles</span>
        </template>
        <template #jayChou>
          <span class="text-neutral-white">Jay Chou</span>
        </template>
      </section-tab>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import BaseSteppers from '@/components/Stepper/BaseSteppers.vue';
import { SectionTab, type Tab } from '@/components/SectionTab';

const activeStep = ref(1);
const tabs = ref<Tab[]>([
  { name: 'oasis', tab: 'Oasis' },
  { name: 'theBeatles', tab: 'the Beatles' },
  { name: 'jayChou', tab: 'Jay Chou' },
]);

const tab = ref('oasis');
</script>

<style scoped></style>
