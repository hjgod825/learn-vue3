<template>
	<div>
		<p>{{ counter }}</p>
		<p>{{ Message }}</p>
		<button v-on:click="increment">일단 늘려~~</button>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const counter = ref(0);
		const Message = ref('HelloVue3');
		const increment = () => {
			counter.value++;
			Message.value += '!';
		};
		return {
			counter,
			Message,
			increment,
		};
	},
};
</script>

<style lang="scss" scoped></style>
