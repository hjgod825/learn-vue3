<template>
	<div>
		<button v-on:click="increment">Click {{ stat.count }}</button>
		<button v-on:click="incrementdeep">Click {{ stat.deep.count }}</button>
	</div>
</template>

<script>
import { reactive } from 'vue';

export default {
	setup() {
		const stat = reactive({
			count: 0,
			deep: {
				count: 0,
			},
		});
		const incrementdeep = () => {
			stat.deep.count++;
		};
		const increment = () => {
			stat.count++;
		};
		return {
			stat,
			increment,
			incrementdeep,
		};
	},
};
</script>

<style lang="scss" scoped></style>
