<template>
	<div>
		<h2>보간법</h2>
		<p>
			{{ message }}
		</p>
		<p v-once>
			{{ message }}
		</p>
		<button v-on:click="message += '!'"></button>
		<hr />
		<h2>HTML</h2>
		<p>{{ rowHtml }}</p>
		<p v-html="rowHtml"></p>
		<h2>속성 바인딩</h2>
		<div v-bind:title="dynamicTitle">마우스를 올려보세요</div>
		<input type="text" value="홍길동" v-bind:disabled="isInputdisabled" />
		<button v-on:click="ablechange">활성화버튼</button>
		<input v-bind="attrs" />
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const message = ref('hello!');
		const rowHtml = ref('<strong>안녕하세요</strong>');
		const dynamicTitle = ref('안녕하세요 동적바인드 입니다');
		const isInputdisabled = ref(true);
		const attrs = ref({
			type: 'password',
			value: '1234568',
			disabled: false,
		});
		const ablechange = () => {
			if (isInputdisabled.value === true) {
				isInputdisabled.value = false;
			} else {
				isInputdisabled.value = true;
			}
		};
		return {
			message,
			rowHtml,
			dynamicTitle,
			isInputdisabled,
			attrs,
			ablechange,
		};
	},
};
</script>

<style lang="scss" scoped></style>
