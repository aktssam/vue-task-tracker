<template>
	<div
		@dblclick="$emit('toggle-reminder', task.id)"
		:class="[task.reminder ? 'reminder' : '', 'task']"
		title="Double click for toggling reminder 🔔"
	>
		<div class="content">
			<h3>{{ task.text }}</h3>
			<p>
				<i class="fa fa-calendar-day"></i> {{ task.date }}&nbsp;&nbsp;
				<i class="fa fa-clock"></i> {{ task.time }}
			</p>
		</div>
		<div class="action">
			<i
				@click="$emit('delete-task', task.id)"
				class="fa-regular fa-trash-can"
			></i>
		</div>
	</div>
</template>

<script>
export default {
	name: 'Task',
	props: { task: Object },
}
</script>

<style scoped>
p i.fa {
	color: rgb(36, 36, 37);
}
.fa-regular {
	color: red;
}
.task {
	user-select: none;
	-webkit-user-select: none;
	-moz-user-select: none;
	-ms-user-select: none;

	display: flex;
	margin: 16px 0px;
	padding: 10px 15px;
	align-items: center;
	justify-content: space-between;
	cursor: crosshair;
	border: none;
	border-radius: 5px;
	outline: 2px solid rgba(0, 0, 0);
	background-color: white;
}
.task.reminder {
	border-left: 8px solid rgb(80, 233, 126);
}
</style>