<template>
  <div>
    <ul class="flex items-center text-body2 text-neutral-white">
      <li
        class="group relative cursor-pointer px-6 py-4 text-body2 font-bold transition-colors duration-300 hover:text-primary-100 desktop:text-body"
        :class="tab.name === value ? 'active text-primary-100' : undefined"
        v-for="tab of tabs"
        :key="tab.name"
        @click="emit('update:value', tab.name)"
      >
        {{ tab.tab }}
        <span
          class="absolute bottom-1 left-1/2 h-1 w-8 -translate-x-1/2 rounded-[10px] bg-[transparent] transition-colors duration-300 group-hover:bg-primary-100 group-[.active]:bg-primary-100"
        ></span>
      </li>
    </ul>
    <TransitionGroup
      name="list"
      tag="ul"
      :onBeforeLeave="onBeforeLeave"
      enter-active-class="transition transition-opacity duration-150 delay-150"
      leave-active-class="transition transition-opacity duration-150"
      enter-from-class="opacity-0"
      leave-to-class="opacity-0"
    >
      <template v-for="tab of tabs" :key="tab.name">
        <li class="w-full" v-if="tab.name === value">
          <slot :name="tab.name" />
        </li>
      </template>
    </TransitionGroup>
    <!-- <ul>
      <li v-for="tab of tabs" :key="tab.name" class="w-full" v-show="tab.name === value">
        <slot :name="tab.name" />
      </li>
    </ul> -->
  </div>
</template>

<script setup lang="ts" generic="T extends Tab">
import { toRefs } from 'vue';
import type { Tab } from './types';

type Props = Partial<{
  tabs: Tab[];
  value: string;
}>;

const props = withDefaults(defineProps<Props>(), {
  tabs: () => [],
  value: undefined,
});
const emit = defineEmits<{ 'update:value': [string] }>();

const { tabs, value } = toRefs(props);

function onBeforeLeave(el: Element): void {
  (el as HTMLElement).style.height = '0px';
}
</script>

<style scoped></style>
