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
			<div class="reminder">
				<input
					v-model="reminder"
					type="checkbox"
					name="reminder"
					id="reminder"
				/>
				<label for="reminder">Set Reminder &nbsp;&nbsp; </label>
			</div>
			<small>*you can double click the task to set reminder later</small>

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
			reminder: false,
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
			this.reminder = false
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

.reminder {
	display: flex;
	justify-content: flex-start;
	align-items: center;
}

input#reminder {
	width: auto;
	margin-right: 8px;
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

small {
	font-size: 12px;
}
</style>