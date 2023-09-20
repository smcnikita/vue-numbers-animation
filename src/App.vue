<script setup lang="ts">
import { onMounted, ref } from "vue";

const number = ref(0);

const change = () => {
	const step = 1000;
	const stopNumber = 1000000;
	let num = 0;

	const interval = setInterval(() => {
		num = num + step;
		if (num >= stopNumber) {
			clearInterval(interval);
			number.value = stopNumber;
		} else {
			number.value = num;
		}
	}, Infinity);
};

onMounted(() => {
	change();
});
</script>

<template>
	<main class="main">
		<div class="main-number">{{ number }}</div>
		<a href="https://github.com/smcnikita" class="main-link">smcnikita</a>
	</main>
</template>

<style scoped>
.main {
	height: 100vh;

	display: flex;
	justify-content: center;
	align-items: center;
	flex-direction: column;
	gap: 16px;
}

.main-number {
	font-size: 50px;
}

.main-link {
	color: #fff;
	text-decoration: none;
	border-radius: 10px;

	padding: 8px;
}

.main-link:focus-visible {
	outline: 2px solid #fff;
}
</style>
