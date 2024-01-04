<template>
  <li class="flex items-center">
    <div class="flex flex-col items-center justify-center gap-y-1">
      <span
        class="flex h-[32px] w-[32px] items-center justify-center rounded-full transition-colors duration-300"
        :class="
          active ? 'bg-primary-100 text-neutral-white' : 'border border-neutral-60 text-neutral-60'
        "
      >
        <transition name="fade" mode="out-in">
          <ic_check v-if="active" />
          <span v-else>{{ indicator }}</span>
        </transition>
      </span>
      <span
        class="text-xs md:text-base md:leading-6 font-bold leading-[21px] transition-colors duration-300"
        :class="active ? 'text-neutral-white' : 'text-neutral-60'"
        ><slot
      /></span>
    </div>
    <slot v-if="showSeparator" name="separator" />
  </li>
</template>

<script setup lang="ts">
import { toRefs } from 'vue';
import ic_check from '@/assets/icons/ic_check.vue';

interface Props {
  active: boolean;
  showSeparator?: boolean;
  indicator: number;
}

const props = withDefaults(defineProps<Props>(), {
  active: false,
  showSeparator: true,
});

const { active, showSeparator } = toRefs(props);
</script>

<style scoped></style>
