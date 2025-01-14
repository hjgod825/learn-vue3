<template>
	<div>
		<p>{{ message }}</p>
		<button v-on:click="addmessage">add cilck</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const message = ref('hello vue');

		const addmessage = () => {
			message.value += '!';
		};

		return {
			message,
			addmessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
