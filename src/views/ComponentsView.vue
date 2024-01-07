<template>
  <div class="w-dvh h-dvh bg-neutral-40">

    <CustomInput class="max-w-60 my-7" v-model:inputValue="name"></CustomInput>
    <CustomButton class="max-w-60 my-7" buttonType="primary">
      <IconChecked class="h-6 w-6" />
    </CustomButton>
    <CustomHeroButton class="my-7"></CustomHeroButton>
    <CustomCheckbox class="my-7" v-model:checked="isChecked" id="myCheckbox" label="My Checkbox" />
      {{ name }}
      {{ isChecked }}
    <CustomDropdown :options="selectOptions" v-model:selectedOption="selectOption"></CustomDropdown>
    {{ selectOption }}
    </div>
</template>

<script setup lang="ts">
import CustomInput from "@/components/CustomInput.vue"
import CustomButton from "@/components/CustomButton.vue"
import CustomHeroButton from "@/components/CustomHeroButton.vue"
import CustomCheckbox from "@/components/CustomCheckbox.vue"
import CustomDropdown from "@/components/CustomDropdown.vue"
import IconChecked from "@/components/icons/IconChecked.vue"

import { ref, reactive } from 'vue';
const name = ref('');

const isChecked = ref(true);
const selectOption = ref(null);
const selectOptions = reactive([
  {
    label: 'please select',
    value: 0
  },
  {
    label: 'a',
    value: 1
  },
  {
    label: 'b',
    value: 2
  },
  {
    label: 'c',
    value: 3
  },
]);

</script>

<style scoped>
</style>