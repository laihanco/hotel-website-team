<template>
  <div class="fixed inset-0 z-50 flex items-center justify-center bg-neutral-40 bg-opacity-40">
    <div class="mx-auto w-full max-w-md rounded-lg bg-neutral-white desktop:w-1/2">
      <!-- Header -->
      <div class="flex justify-between">
        <h5 class="text-subtitle">{{ props.title }}</h5>
        <button>
          <icClose class="h-[40px] w-[40px] cursor-pointer p-2" />
        </button>
      </div>

      <!-- Content -->
      <div class="p-10 text-center">
        <slot> {{ props.content }} </slot>
      </div>

      <!-- Footer -->
      <slot name="footer">
        <div class="flex justify-center gap-x-4 border-t border-neutral-40 p-3">
          <!-- TODO 等 button 元件出來做替換 -->
          <button class="w-full rounded border border-primary-100 px-8 py-2 text-primary-100">
            按鈕1
          </button>
          <button class="w-full rounded bg-primary-100 px-8 py-2 text-neutral-white">按鈕2</button>
        </div>
      </slot>
    </div>
  </div>
</template>

<script setup lang="ts">
import { defineProps } from 'vue';
import icClose from '@/assets/icons/icClose.vue';

type Props = Partial<{
  title: string;
  content: string;
}>;

const props = withDefaults(defineProps<Props>(), {
  title: '',
  content: '請輸入文字...',
});
</script>

<style scoped>
* {
  outline: 1px solid salmon;
}
</style>
