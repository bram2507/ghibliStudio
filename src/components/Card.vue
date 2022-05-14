<template>
	<div class="main_card"></div>
</template>
<script>
export default {
	name: "Card",
};
</script>
<style scoped>
.main_card {
	display: flex;
	justify-content: center;
	justify-items: center;
	width: 25vw;
	min-height: 55vh;
	border-radius: 2vh;
	background-color: #fff;
	transition: 0.3s ease-in-out;
}
.main_card:hover {
	transition: 0.3s ease-in-out;
	transform: scale(1.2);
}
</style>