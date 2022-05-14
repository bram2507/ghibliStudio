<template>
	<div class="main_card">
		<div class="main_card__poster">
			<img :src="film.image" alt="" />
		</div>
		<div>
			<div></div>
			<div></div>
		</div>
	</div>
</template>
<script>
export default {
	name: "Card",
	props: {
		film: Object,
		characters: Object,
	},
	data() {
		return {};
	},
	watch: {},
	computed: {},
	created() {},
	mounted() {},
};
</script>
<style scoped>
.main_card {
	display: flex;
	justify-content: center;
	justify-items: center;
	width: 45%;
	flex-direction: column;
	min-height: 35vh;
	border-radius: 2vh;
	background-color: #fff;
	transition: 0.3s ease-in-out;
	margin-top: 3vh;
}
.main_card:hover {
	transition: 0.3s ease-in-out;
	transform: scale(1.1);
}
.main_card__poster {
	width: 150px;
	height: auto;
}

.main_card__poster img {
	width: 100%;
	height: 100%;
	image-rendering: optimizeQuality;
	border-radius: 0.5vh;
}
</style>