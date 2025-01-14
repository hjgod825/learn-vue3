<template>
	<div>
		<h1>반응형 메세지</h1>
		<p>{{ reactiveMessage }}</p>
		<button v-on:click="addReactiveMessage">!추가 버튼</button>
		<h1>일반 메세지</h1>
		<p>{{ normalMessage }}</p>
	</div>
</template>

<script>
import { ref, onMounted, onBeforeMount } from 'vue';
export default {
	name: 'App',
	setup() {
		console.log('setup');
		const reactiveMessage = ref('Hello Reactive Message');
		const normalMessage = 'Hello Nornmal Message';

		const addReactiveMessage = () => {
			reactiveMessage.value += '!';
		};

		// console.log('isRef(reactiveMessage) :', isRef(reactiveMessage));

		onMounted(() => {
			console.log('onMounted');
		});

		onBeforeMount(() => {
			console.log('beforeMount');
		});

		return {
			reactiveMessage,
			normalMessage,
			addReactiveMessage,
		};
	},
};
</script>

<style lang="scss" scoped></style>
