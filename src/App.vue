<template>
	<div id="Todo">
		<img alt="Vue logo" src="./assets/logo.png" />
		<h1>{{nameApp}}</h1>
		<Tabla />
	</div>
</template>



<script>
import Tabla from './components/Tabla.vue';

export default {
	nameApp: '#Todo',

	data() {
		return {
			nameApp: 'ToDo list con Vue.Js',
		};
	},
	components: {
		Tabla,
	},
};
</script>



<style>
body {
	background-image: url('https://media.licdn.com/dms/image/C4D1BAQE1fJX_KigWcw/company-background_10000/0?e=2159024400&v=beta&t=Avi3u2YvF3KtNJWg3q571ugBYW80zrfJ52n7sQ9d2tU');
}

#Todo {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #eeeeee;
	margin-top: 60px;
}
</style>
