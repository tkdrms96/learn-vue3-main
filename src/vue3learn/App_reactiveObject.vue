<template>
	<div></div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
	setup() {
		const count = ref(0);
		const state = reactive({
			count,
		});

		console.log(count.value); // count 를 접근할때는 value를 써야함 이것을 만약에 reactive로 object 타입으로 묶었을 때
		// console.log(state.count.value); undefined
		console.log(state.count); // 값 출력

		const messasge = ref('hello');
		const messageArr = reactive([messasge]);

		/* 배열에 경우 위에 오브젝트에서 접근 방식과 다름*/

		console.log('arr[0] :', messageArr[0].value); // ref으로 선언한것을 arr로 래핑하게 되면 value를 붕텨줘야함
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
