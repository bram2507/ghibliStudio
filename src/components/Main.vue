<template>
	<div class="main_content">
		<!-- <div class="main_content__title"></div> -->
		<Card :film="film" v-for="(film, key) in films" :key="key" />
	</div>
</template>

<script>
import Card from "./Card.vue";
export default {
	props: {},
	components: {
		Card,
	},
	data() {
		return {
			films: null,
			characters: null,
		};
	},
	created() {
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
}
.main_content {
	width: 100%;
	min-height: 100vh;
	background-color: #d4f1f4;
	display: flex;
	justify-content: center;
	align-items: center;
	flex-direction: column;
}

.main_content__title {
	margin-top: 5vh;
	margin-top: 5vh;
}
</style>
