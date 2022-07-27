<template>
	<header>
		<h1>{{ title }}</h1>
		<Button
			@btn-toggle="$emit('btn-toggle')"
			:text="showAddTask ? 'Close' : 'Add Task'"
			:color="showAddTask ? '#db4e35' : ''"
		/>
	</header>
</template>

<script>
import Button from './Button.vue'

export default {
	name: 'Header',
	props: {
		title: String,
		showAddTask: Boolean,
	},
	components: {
		Button,
	},
	emits: ['btn-toggle'],
}
</script>

<style scoped>
header {
	display: flex;
	justify-content: space-between;
	align-items: center;
	margin-bottom: 20px;
}
</style>