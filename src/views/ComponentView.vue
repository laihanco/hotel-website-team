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
import { ref, reactive } from 'vue';
import BaseSteppers from '@/components/Stepper/BaseSteppers.vue';
import CustomInput from "@/components/CustomInput.vue"
import CustomButton from "@/components/CustomButton.vue"
import CustomHeroButton from "@/components/CustomHeroButton.vue"
import CustomCheckbox from "@/components/CustomCheckbox.vue"
import CustomDropdown from "@/components/CustomDropdown.vue"
import IconChecked from "@/components/icons/IconChecked.vue"

const activeStep = ref(1);
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

<style scoped></style>
