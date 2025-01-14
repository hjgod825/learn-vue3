<template>
	<div></div>
</template>

<script>
import { ref, reactive } from 'vue';
export default {
	setup() {
		//ref -> object 객체에서 사용함
		const count = ref(0);
		const state = reactive({
			count,
		});
		count.value++;
		count.value++;
		console.log(count.value);
		console.log('state.count :', state.count);
		//ref => Array 배열에서 사용함
		const message = ref('Hello');
		const arr = reactive([message]);
		console.log('arr[0] : ', arr[0].value);
		return {
			// state
		};
	},
};
</script>

<style lang="scss" scoped></style>
