<script>
export default {
	data() {
		return {
			notes: [
				{title: 'Дописать диплом', category: 'Учеба', 
				text:'Нужно дописать первую теоретическую главу по диплому и отправить руководителю до следующей недели'},

				{title: 'Прогулка', category: 'Важное', 
				text:'11 апреля важная встреча по адресу Россия, 123242, г. Москва, ул.Садовая-Кудринская, д. 5, стр. 1 в 14.30'}
			],
			category: ``,
			title: ``,
			text: ``
		};
	},

	methods: {
		save() {
			this.notes.push({title: this.title, category: this.category, text: this.text});
			this.title = ``;
			this.category = ``;
			this.text = ``;

		}
	}
};
</script>

<template>
	<div class="notes-app container">
		<div class="row row-cols-2 g-3 mt-3">
			<!-- Форма -->
			<div class="col notes-app-form">
				<div class="form-floating">
					<input type="text" class="form-control" id="title" v-model="title"/>
					<label for="title">Название</label>
				</div>
				<div class="form-floating my-3">
					<select class="form-select" id="category" v-model="category">
						<option>Без категории</option>
						<option>Важное</option>
						<option >Учёба</option>
					</select>
					<label for="category">Категория</label>
				</div>
				<textarea
					class="form-control my-3"
					rows="5"
					id="text"
					placeholder="Введите текст"
					v-model="text"
				></textarea>
				<div class="btn-group d-flex justify-content-center my-3">
					<button type="button" class="btn btn-outline-secondary" @click="save()">
						Сохранить
					</button>
				</div>
			</div>

			<!-- Заметки -->
			<div class="col">
				<div class="row row-cols-2 notes-container">
					<div class="col my-2" v-for="note in notes">
						<div class="card">
							<div class="card-body" :class="{'important': note.category == 'Важное', 'study': note.category == 'Учёба'}">
								<h6 class="card-subtitle mb-2 text-muted">{{ note.category }}</h6>
								<p class="card-text">{{ note.text }}</p>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<style scoped>
.important {
	background-color: rgba(224, 105, 240, 0.664);
}

.study {
	background-color: rgb(140, 240, 140);
}

.notes-app {
	max-width: 1000px;
}
.col.notes-app-form {
	margin-top: 20px;
}
</style>
