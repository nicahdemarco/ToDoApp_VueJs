<template>
	<div>
		<div class="Agregar">
			<form class="formulario form-inline" @submit.prevent="addTask">
				<div class="col">
					<input
						type="text"
						class="form-control"
						placeholder="Agrega una tarea nueva"
						v-model="inputData"
					/>
					<input type="submit" value="+" class="btn btn-info" />
				</div>
			</form>
		</div>

		<div class="container">
			<table class="table">
				<thead>
					<tr>
						<th>Hecho!</th>
						<th>Tarea</th>
						<th>Accion</th>
					</tr>
				</thead>

				<tbody>
					<tr v-for="tarea in tareas" :key="tarea.title">
						<td>
							<input type="checkbox" v-model="tarea.done" />
						</td>
						<td :class="{taskDone:tarea.done}">{{tarea.title}}</td>
						<td>
							<button class="btn btn-danger" @click="deleteTask(tarea)">Eliminar</button>
						</td>
					</tr>
				</tbody>
			</table>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			inputData: '',
			tareas: [
				{
					title: 'task1',
					done: true,
				},

				{
					title: 'task2',
					done: true,
				},

				{
					title: 'task3',
					done: false,
				},
			],
		};
	},

	methods: {
		// Funcion para agregar tareas
		addTask() {
			if (this.inputData !== '') {
				let inputData = this.inputData;
				this.inputData = '';
				return this.tareas.push({
					title: inputData,
					done: false,
				});
			} else {
				return alert('Agrega una tarea');
			}
		},
		// Funcion para borrar tareas
		deleteTask(tarea) {
			this.tareas.splice(this.tareas.indexOf(tarea), 1);
			alert('Tarea eliminada');
		},
	},
};
</script>

<style scoped>
.container {
	background-color: rgb(245, 245, 223);
}

.agregar {
	margin: 2%;
	display: inline-block;
}

.formulario {
	margin: 1%;
	width: 100%;
}
.btn-info {
	margin: 1%;
}

.taskDone {
	text-decoration: line-through;
	color: grey;
}
</style>

