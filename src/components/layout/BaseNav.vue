<template>
  <nav
    class="index-50 flex w-full content-center justify-between bg-neutral-black px-3 py-4 text-neutral-white desktop:px-20 desktop:py-6"
  >
    <img src="@/assets/LOGO.svg" alt="LOGO" class="w-[110px] desktop:w-[198px]" />

    <!-- 手機-選單開啟鈕 -->
    <icMenu class="h-[40px] w-[40px] cursor-pointer p-2 desktop:hidden" @click="showMenu = true" />

    <!-- 手機-選單內容 -->
    <div
      v-show="showMenu"
      class="absolute left-0 top-0 h-full w-full bg-neutral-black p-5 desktop:hidden"
    >
      <ul class="flex h-full flex-col justify-center gap-4 text-center" @click="closeMenu">
        <li>
          <router-link class="w-full cursor-pointer p-4" to="/rooms">客房旅宿</router-link>
        </li>
        <li>
          <router-link class="w-full cursor-pointer p-4" to="/login">會員登入</router-link>
        </li>
        <li class="rounded-lg bg-primary-100">
          <router-link class="w-full cursor-pointer p-4" to="/booking"> 立即訂房 </router-link>
        </li>
      </ul>
    </div>

    <!-- 手機-選單關閉鈕 -->
    <icClose
      v-show="showMenu"
      class="absolute right-5 top-5 h-[48px] w-[48px] cursor-pointer p-2"
      @click="showMenu = false"
    />

    <!-- 桌機-選單內容 -->
    <ul class="hidden items-center gap-4 desktop:flex">
      <li>
        <router-link class="cursor-pointer p-4" to="/rooms">客房旅宿</router-link>
      </li>
      <li>
        <router-link class="cursor-pointer p-4" to="/login">會員登入</router-link>
      </li>
      <li class="rounded-lg bg-primary-100">
        <router-link class="cursor-pointer p-4" to="/booking"> 立即訂房 </router-link>
      </li>
    </ul>
  </nav>
</template>

<script setup lang="ts">
import { ref, Ref } from 'vue';
import icMenu from '@/assets/icons/icMenu.vue';
import icClose from '@/assets/icons/icClose.vue';

const showMenu: Ref<boolean> = ref(false);

const closeMenu = (e: PointerEvent) => {
  if ((e.target as HTMLElement).nodeName === 'A') showMenu.value = false;
};
</script>

<style scoped></style>
