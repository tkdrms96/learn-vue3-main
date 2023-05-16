<template>
	<div></div>
</template>

<script>
import { reactive, toRefs } from 'vue';

export default {
	setup() {
		const book = reactive({
			author: 'vue team',
			year: '2020',
			title: 'vue 3 guide',
			description: '당신은 지금 바로 이 챙글 읽습니다.',
			priec: '무료',
		});
		// 구조 분해 할당시 toRefs 함수를 사용하여 반응형을 잃지 않을 수 있음.
		const { author, year } = toRefs(book);

		// const test = toRefs[...book];
		return { author, year, book };
	},
};
</script>

<style lang="scss" scoped></style>
