<template>
  <li class="flex items-center">
    <div class="flex flex-col items-center justify-center gap-y-1">
      <span
        class="flex h-[32px] w-[32px] items-center justify-center rounded-full transition-colors duration-300"
        :class="active ? 'bg-primary-100 text-[#fff]' : 'border border-neutral-60 text-neutral-60'"
        >1</span
      >
      <span
        class="text-xs md:text-base md:leading-6 font-bold leading-[21px] transition-colors duration-300"
        :class="active ? 'text-[#fff]' : 'text-neutral-60'"
        ><slot
      /></span>
    </div>
    <slot v-if="showSeparator" name="separator" />
  </li>
</template>

<script setup lang="ts">
import { toRefs } from 'vue';

interface Props {
  active: boolean;
  showSeparator?: boolean;
}

const props = withDefaults(defineProps<Props>(), {
  active: false,
  showSeparator: true,
});

const { active, showSeparator } = toRefs(props);
</script>

<style scoped>
.step-primary {
  @apply bg-primary-100;
}
</style>
