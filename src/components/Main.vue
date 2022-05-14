<template>
	<div class="main_content">
		<div class="main_content__title">
			<img src="@/assets/ghibli-logo.svg" alt="" />
		</div>
		<div>
			<h1>Entrar</h1>
		</div>
	</div>
</template>

<script>
// import Card from "./Card.vue";
export default {
	props: {},
	// components: {
	// 	Card,
	// },
	data() {
		return {
			show: false,
			films: null,
			characters: null,
		};
	},
	created() {
		setTimeout(() => {
			this.show = !this.show;
		}, 1000);
		const characters = "https://ghibliapi.herokuapp.com/people";
		const films = "https://ghibliapi.herokuapp.com/films";
		const apiResp = this.getGhibliFilms(films);
		apiResp.then((response) => {
			this.films = response;
			console.log(this.films);
		});

		const apiResp2 = this.getGhibliCharacters(characters);
		apiResp2.then((response) => {
			this.characters = response;
			console.log(this.characters);
		});
	},
	methods: {
		getGhibliFilms(url) {
			const response = fetch(url)
				.then((response) => response.json())
				.then((data) => {
					return data;
				});
			return response;
		},
		getGhibliCharacters(url) {
			const response = fetch(url)
				.then((response) => response.json())
				.then((data) => {
					return data;
				});
			return response;
		},
	},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
	padding: 0;
	margin: 0;
	box-sizing: border-box;
	--curious-blue: #1c9ccc;
	--gin: #e3eee9;
	--tiber: #082a3e;
	--blumine: #1c5e79;
	--downy: #6fb7ce;
	--jelly-bean: #2a7d9c;
	--cello: #1d4c5a;
	--seagull: #86d5e9;
	--matisse: #176b94;
	font-family: "Amaranth", sans-serif;
}
.main_content {
	width: 100%;
	min-height: 100vh;
	display: flex;
	justify-content: center;
	align-items: center;
	flex-direction: column;
	background-color: var(--curious-blue);
}

.main_content__title {
	display: flex;
	justify-content: center;
	align-items: center;
}
.main_content__title img {
	width: 55vw;
	height: auto;
	image-rendering: optimizeQuality;
}
</style>
