<template>
	<p>보관법</p>
	<div>
		<h1>
			{{ message }}
		</h1>
	</div>
	<button @click="addMessage">addMessage</button>
	<div>Html</div>
	<h2 v-html="addHtml"></h2>
	<h2>{{ addHtml }}</h2>
	<div><h1>input style</h1></div>
	<input type="text" :disabled="isDisabled" value="홍길동" />
	<input v-bind="attrs" />

	<input type="text" v-model="textWatch" />
	<p>{{ textWatch }}</p>
</template>

<script>
import { ref, watch, computed } from 'vue';

export default {
	setup() {
		const message = ref('안녕하세요!');
		const addMessage = () => {
			message.value = message.value + '!';
		};
		const addHtml = ref('<strong>안녕하세요 ㅋㅋ</strong>');

		const isDisabled = ref(false);

		const attrs = ref({
			type: 'text',
			value: 'ㅋㅋ',
			disabled: false,
		});

		const textWatch = ref('');

		computed('textWatch', () => {
			console.log('지켜보고있겠다');
		});

		return {
			message,
			addMessage,
			addHtml,
			isDisabled,
			attrs,
			textWatch,
		};
	},
};
</script>

<style lang="scss" scoped></style>
