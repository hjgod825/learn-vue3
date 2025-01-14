<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<h3>강의가 있습니까?</h3>
		<!-- <p>{{ teacher.leactures.length > 0 ? '있음' : '없음' }}</p> -->
		{{ hasLeactures }}
		{{ existLecture() }}
		<button @click="count++">count : {{ count }}</button>
		<h2>{{ fullname }}</h2>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup() {
		const teacher = reactive({
			name: '짐코딩',
			leactures: ['HTML/CSS', 'JavaScripts', 'Vue3'],
		});
		const hasLeactures = computed(() => {
			return teacher.leactures.length > 0 ? '있음' : '없음';
		});

		const existLecture = () => {
			return teacher.leactures.length > 0 ? '있음' : '없음';
		};

		const count = ref(0);

		const firstname = ref('lee');
		const lastname = ref('hyeonghju');
		const fullname = computed({
			get() {
				return firstname.value + '' + lastname.value;
			},
			set(value) {
				[firstname.value, lastname.value] = value.split(' ');
			},
		});

		fullname.value = '이 형주';

		return {
			teacher,
			hasLeactures,
			count,
			fullname,
			existLecture,
		};
	},
};
</script>

<style lang="scss" scoped></style>
