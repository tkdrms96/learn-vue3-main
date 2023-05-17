<template>
	<div>
		<h2>input Value</h2>
		<!-- <input type="text" v-model="inputValue" /> -->
		<h2>input Value lazy</h2>
		<!-- 포커스가 떨어진 이후 동기화시켜줌 lazy-->
		<input type="text" v-model.lazy="inputValue" />
		<h2>input Value number</h2>
		<!-- 바로 사칙연산을 수행하여야할 때 number타입 지정 -->
		<input type="text" v-model.number="inputValue" />
		<h2>input Value trim</h2>
		<!-- 사용자가 공백을 추가하더라도 공백을 제거해주는 trim 수식어 -->
		<input type="text" v-model.trim="inputValue" />
		<h2>{{ inputValue }}</h2>

		<h2>checkbox value</h2>
		<label for="checkbox">{{ checkboxValue }}</label>
		<input type="checkbox" id="checkbox" v-model="checkboxValue" />
		<!-- <input
			type="checkbox"
			id="checkbox"
			:checked="checkboxValue"
			@change="event => (checkboxValue = event.target.checked)"
		/> -->
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const inputValue = ref(null);
		const checkboxValue = ref(true);
		return { inputValue, checkboxValue };
	},
};
</script>

<style lang="scss" scoped></style>
