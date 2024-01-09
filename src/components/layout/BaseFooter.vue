<template>
  <footer
    class="flex flex-col flex-wrap bg-neutral-bg px-3 py-20 text-neutral-white desktop:flex-row desktop:px-40"
  >
    <div class="mb-20 flex w-full flex-col flex-wrap justify-between desktop:flex-row">
      <div class="mb-20 mr-20">
        <img src="@/assets/LOGO.svg" alt="LOGO" class="mb-10 w-[196px]" />

        <img
          src="@/assets/icons/ic_line.svg"
          alt="line"
          class="mr-4 inline-block rounded-full border p-2"
        />
        <img
          src="@/assets/icons/ic_ig.svg"
          alt="instagram"
          class="inline-block rounded-full border p-2"
        />
      </div>

      <div class="flex flex-col gap-x-20 gap-y-4 desktop:flex-row">
        <div class="flex flex-col gap-y-4">
          <div class="desktop:mb-10">
            <p class="mb-2 text-title">TEL</p>
            <p class="text-body2">+886-7-1234567</p>
          </div>
          <div>
            <p class="mb-2 text-title">FAX</p>
            <p class="text-body2">+886-7-1234567</p>
          </div>
        </div>

        <div class="flex flex-col gap-y-4">
          <div class="desktop:mb-10">
            <p class="mb-2 text-title">MAIL</p>
            <p class="text-body2">elh@hexschool.com</p>
          </div>
          <div>
            <p class="mb-2 text-title">WEB</p>
            <p class="text-body2">www.elhhexschool.com.tw</p>
          </div>
        </div>
      </div>
    </div>

    <div class="flex w-full flex-col flex-wrap justify-between gap-y-4 text-body2 desktop:flex-row">
      <p>806023 台灣高雄市新興區六角路123號</p>
      <p>© 享樂酒店 2023 All Rights Reserved.</p>
    </div>
  </footer>
</template>

<script setup lang="ts"></script>

<style scoped></style>
