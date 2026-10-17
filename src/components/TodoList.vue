<script>

export default {
    data() {
        return {
            todos: [{title: 'Дописать первую главу диплома', isDone: false}, 
                    {title: 'Сдать долги по веб-курсу', isDone: false}, 
                    {title: 'Снять видео-интервью для практики', isDone: false}, 
                    {title: 'Начать делать курсовую', isDone: false},
                    {title: 'Отправить письмо на практику', isDone: true}],

            newTask: ``
        }
    },

    methods: {
        toggle(item) {
            item.isDone = !item.isDone
        },

        add() {
            let newTask = {title: this.newTask, isDone: false}
            this.todos.push(newTask)
            this.newTask = ``
        }
    }
}
</script>

<template>
    <div class="todo-list">
        <div class="input-group mb-3">
            <input  type="text"
                    class="form-control" v-model="newTask">

            <button class="btn btn-outline-secondary"
                    type="button" @click="add">
                    Добавить
            </button>
        </div>

        <ul class="list-group">

            <!-- Вёрстка одной тудушки -->
            <li class="list-group-item" v-for="item in todos" :class="{'done': item.isDone}">
                <div class="input-group">
                    <div class="input-group-text">
                        <input v-model="item.isDone"
                        class="form-check-input mt-0"
                                type="checkbox">
                    </div>
                    <span class="input-group-text todo-title" @click="toggle(item)">
                        {{item.title}}
                    </span>
                    <button class="btn btn-outline-secondary"
                            type="button">
                        X
                    </button>
                </div>
            </li>
            <!-- Конец вёрстки -->
            
        </ul>
    </div>
</template>

<style scoped>
.todo-title {
    flex: 1;
}
.input-group {
    cursor: pointer;
}
.done .todo-title {
    text-decoration: line-through;
}
</style>