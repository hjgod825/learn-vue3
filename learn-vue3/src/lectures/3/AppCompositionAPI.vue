<template>
	<div>
		<button v-on:click="increment">counter : {{ counter }}</button>
	</div>
</template>

<script>
import { onMounted, ref } from 'vue';
export default {
	setup() {
		const counter = ref(0);
		const increment = () => {
			counter.value++;
		};

		onMounted(() => {
			console.log('마운트됨');
		});

		return {
			counter,
			increment,
			onMounted,
		};
	},
};
</script>

<style lang="scss" scoped></style>
