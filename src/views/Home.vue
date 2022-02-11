<template>

	<button v-on:click="fetchNew">Get new</button>
</template>

<script>

export default {
	name: 'home',
	data() {
		return {
			
		}
	},
	created() {
		this.fetchNew();
		this.getWaves();
	},

	methods: {
		async fetchNew() {
			const url = 'https://goweather.herokuapp.com/weather/hoddevik';
			const res = await fetch(url);
			const { object }   = await res.json();
			//console.log(wind)
		},
		async getWaves() {
			const url = 'https://api.stormglass.io/v2/weather/point?lat=45.440845&lng=12.315515&params=';
			const options = {
				headers: {
					'Authorization': '7e4e1274-8b24-11ec-96e0-0242ac130002-7e4e1300-8b24-11ec-96e0-0242ac130002'
				}
			};
			const res =  await fetch(url, options);
			console.log(res);
			const data = await res.json();
			console.log(data);
		}
	},

}
</script>

<style scoped>

</style>

