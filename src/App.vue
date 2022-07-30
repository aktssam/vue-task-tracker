<template>
	<div class="container">
		<Header
			title="Task Tracker"
			@btn-toggle="toggleAddTask"
			:showAddTask="showAddTask"
		/>
		<RouterView :showAddTask="showAddTask" />
	</div>
	<Footer />
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'

export default {
	name: 'App',
	components: {
		Header,
		Footer,
	},
	data() {
		return {
			showAddTask: false,
		}
	},
	methods: {
		toggleAddTask() {
			this.showAddTask = !this.showAddTask
		},
	},
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
	box-sizing: border-box;
	margin: 0;
	padding: 0;
}
body {
	font-family: 'Poppins', sans-serif;
}
.container {
	max-width: 500px;
	margin: 30px auto;
	overflow: auto;
	min-height: 300px;
	border: 2px solid #000;
	padding: 30px;
	background-color: rgb(242, 247, 245);
	box-shadow: 8px 8px #000;
	border-radius: 5px;
}
.btn {
	display: inline-block;
	background-color: rgb(119, 226, 166);
	color: black;
	border: none;
	outline: black solid 2px;
	box-shadow: 7px 8px 2px rgba(0, 0, 0, 0.8);
	padding: 10px 20px;
	margin: 5px;
	border-radius: 5px;
	cursor: pointer;
	text-decoration: none;
	font-size: 15px;
	font-family: inherit;
}

.btn:active {
	transition: 0.3s;
	box-shadow: 0px 0px 1px black;
}

.btn-block {
	display: block;
	width: 100%;
}

hr {
	margin: 20px 0px 10px 0px;
}

footer {
	display: flex;
	justify-content: center;
	margin-bottom: 20px;
}
</style>
