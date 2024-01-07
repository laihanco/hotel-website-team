<template>
	<div class="w-full">
		<div class="flex">
			<div class="text-neutral-white flex-1">label</div>
			<div class="text-primary-100 text-title">必填</div>
		</div>
		<input
			:value="inputValue"
			@input="$emit('update:inputValue', $event.target.value)"
			class="text-neutral-80 w-full p-4 rounded-lg focus:border focus:border-primary-100 solid-shadow outline-none placeholder-neutral-60 "
			:class="isError ? 'border border-alert-100': ''"
			:placeholder="placeholder"
			type="text"
		/>
		<div v-if="isError" class="text-alert-100 text-subtitle">{{ errorMsg }}</div>
	</div>
</template>

<script setup lang="ts">

const props = defineProps({
	label: {
    type: String,
    default: 'label',
  },
  inputValue: {
    type: String,
    default: '',
  },
	placeholder: {
		type: String,
    default: 'Text',
	},
	isError: {
		type: Boolean,
    default: false,
	},
	errorMsg: {
		type: String,
    default: 'Error message',
	}
});

</script>

<style lang="scss" scoped>
.solid-shadow {
	&:focus {
		box-shadow: 0px 0px 0px 2px rgba(190, 156, 124, 0.1)
	}
}
</style>