<template>
	<div>
		<p>book.author : {{ book.author }}</p>
		<p>author : {{ author }}</p>
		<p>book.title : {{ book.title }}</p>
		<p>title : {{ title }}</p>
	</div>
</template>

<script>
import { reactive, toRefs } from 'vue';
export default {
	setup() {
		const book = reactive({
			author: 'Vue Team',
			year: '2020',
			title: 'Vue 3 Guide',
			description: '당신은 지금 바로 이 책을 읽습니다.',
			price: 'freeeeeees',
		});

		const { author, title } = toRefs(book);
		return { book, author, title };
	},
};
</script>

<style lang="scss" scoped></style>
