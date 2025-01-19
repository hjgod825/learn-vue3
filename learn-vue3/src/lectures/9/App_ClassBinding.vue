<template>
	<div>
		<div class="text" :class="classObject">텍스트 입니다.</div>
		<button @click="toggle">toggle</button>
		<button @click="classObject['text-danger'] = !classObject['text-danger']">
			hasError_toggle
		</button>
	</div>
</template>

<script>
import { computed, ref } from 'vue';

export default {
	setup() {
		const isactive = ref(true);

		const hasError = ref(false);

		// const classObject = reactive({
		// 	active: true,
		// 	'text-danger': hasError.value,
		// });
		const classObject = computed(() => {
			return {
				active: true,
				'text-danger': true,
			};
		});

		const toggle = () => {
			isactive.value = !isactive.value;
		};
		return { isactive, hasError, classObject, toggle };
	},
};
</script>

<style scoped>
.active {
	font-weight: 900;
}
.text-danger {
	color: red;
}
</style>
