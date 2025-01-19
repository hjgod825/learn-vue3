<template>
	<div>
		<div :style="styleObject">
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Corrupti nostrum
			quo provident. Recusandae, alias temporibus asperiores dolore aperiam
			optio ab et, totam molestiae quidem architecto reprehenderit sunt tempore
			mollitia iste.
		</div>
		<button @click="fontSize--">-</button>
		<button @click="fontSize++">+</button>
	</div>
</template>

<script>
import { computed, ref } from 'vue';

export default {
	setup() {
		// const styleObject = reactive({
		// 	color: 'red',
		// 	fontSize: '30px',
		// });

		const fontSize = ref(13);

		const styleObject = computed(() => {
			return {
				color: 'red',
				fontSize: fontSize.value + 'px',
			};
		});

		return { styleObject, fontSize };
	},
};
</script>

<style scoped></style>
