<template>
	<div class="add-task">
		<form @submit="onSubmit">
			<label for="text">Enter a task</label>
			<input v-model="text" type="text" name="text" id="text" />

			<label for="date">Date & Time</label>
			<div class="input-group">
				<input v-model="date" type="date" name="date" id="date" />
				<input v-model="time" type="time" name="time" id="time" />
			</div>

			<button class="btn submit">Save Task</button>
		</form>
	</div>
</template>

<script>
export default {
	name: 'AddTask',
	data() {
		return {
			text: '',
			date: '',
			time: '',
			reminder: true,
		}
	},
	methods: {
		onSubmit(e) {
			e.preventDefault()

			if (!this.text) {
				alert('Task field must not empty!')
				return
			}

			const newTask = {
				id: Math.floor(Math.random() * 10000),
				text: this.text,
				date: this.date,
				time: this.time,
				reminder: this.reminder,
			}

			this.$emit('new-task', newTask)

			//reset the form
			this.text = ''
			this.date = ''
			this.time = ''
			this.reminder = ''
		},
	},
}
</script>

<style scoped>
input {
	margin: 10px 0px;
	display: block;
	padding: 10px;
	width: 100%;
}
.input-group {
	display: flex;
}

#date {
	/* .input-group#time { */
	width: 65%;
	margin-right: 5px;
}

#time {
	width: 35%;
}
.btn {
	display: inline-block;
	margin: 10px 0px;
	width: 100%;
	background-color: rgb(182, 202, 245);
	color: black;
}
</style>