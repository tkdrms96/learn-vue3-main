<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<!-- <p>{{ teacher.lectures.length > 0 ? '있음' : '없음 ' }}</p> -->
		<p>{{ hasLecture }}</p>
		<p>{{ hasLecture2 }}</p>
		<p>이름</p>
		<p>{{ fullName }}</p>
	</div>
</template>

<script>
import { computed, reactive } from 'vue';

export default {
	setup() {
		const teacher = reactive({
			name: '짐코딩',
			lectures: ['HTML/CSS', ''],
		});
		/* <p>{{ teacher.lectures.length > 0 ? '있음' : '없음 ' }}</p> <ㅡ 코드가 복잡하고 가독성이 떨어짐 이를 보안하기 위한 computed 속성*/

		const hasLecture = computed(() => {
			return teacher.lectures.length > 0 ? '있음' : '없음 ';
		});
		// 훨씬 코드가 깔끔하게 setup함수에서 코딩할 수 있음
		const hasLecture2 = () => {
			return teacher.lectures.length > 0 ? '있음' : '없음 ';
		};
		// computed 사용한 것이 성능면에서 더 좋음.

		const firstName = 'firstName';
		const lastName = 'lastName';

		const fullName = computed({
			get() {
				return firstName + ' ' + lastName;
			},
			set(value) {
				[firstName.value, lastName.value] = value.split(' ');
			},
		});

		fullName.value = '짐 코딩';
		return {
			teacher,
			hasLecture,
			hasLecture2,
			fullName,
		};
	},
};
</script>

<style lang="scss" scoped></style>
