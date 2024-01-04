<template>
  <svg
    :width="size"
    :height="size"
    viewBox="0 0 16 16"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <g id="ic_check" clip-path="url(#clip0_3214_3212)">
      <path
        id="Vector"
        d="M6.00091 10.8L3.20091 8L2.26758 8.93334L6.00091 12.6667L14.0009 4.66667L13.0676 3.73334L6.00091 10.8Z"
        :fill="color"
      />
    </g>
    <defs>
      <clipPath id="clip0_3214_3212">
        <rect :width="size" :height="size" :fill="color" />
      </clipPath>
    </defs>
  </svg>
</template>

<script setup lang="ts">
import { toRefs } from 'vue';

interface Props {
  color?: 'currentColor' & string;
  size?: number;
}

const props = withDefaults(defineProps<Props>(), {
  color: 'currentColor',
  size: 16,
});

const { color, size } = toRefs(props);
</script>

<style scoped></style>
