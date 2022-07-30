<template>
	<footer>
		<router-link to="/">Home</router-link>
		&nbsp;•&nbsp;
		<router-link to="/about">About</router-link>
		&nbsp;•&nbsp;
		<p>
			made with ❤ aktssam's simple vue app for
			<a
				href="https://www.youtube.com/watch?v=qZXt1Aom3Cs&t=4223s"
				target="_blank"
				>practice</a
			>
		</p>
	</footer>
</template>

<script>
export default {
	name: 'Footer',
}
</script>

<style scoped>
p {
	display: block;
	margin-right: 10px;
}
</style>