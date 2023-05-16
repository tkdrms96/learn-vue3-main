<template>
	<div>
		<button v-on:click="increment">click{{ state.count }}</button>
		<button v-on:click="increment">Deep click{{ state.deep.count }}</button>
	</div>
</template>

<script>
import { reactive, toRefs } from 'vue';

export default {
	setup() {
		/* 반응형 상태(객체) 선언 reactive */
		const state = reactive({
			count: 0,
			deep: {
				count: 0,
			},
		});

		const increment = () => {
			state.count++;
			state.deep.count++;
		};

		return {
			state,
			increment,
		};
	},
};
</script>

<style lang="scss" scoped></style>
