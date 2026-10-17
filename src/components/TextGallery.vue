<script>
export default {
    data() {
        return {
            words: ['Книги', 'Электроника', 'Одежда'],
            index: 0
        }
    },

    methods: {
        next() {
            if (this.index == this.words.length - 1) {
                this.index = 0;
            } else {
                this.index++;
            }
        },

        prev() {
            if (this.index == 0) {
                this.index = this.words.length - 1;
            } else {
                this.index--;
            }
        }
    }
}
</script>

<template>
    <div class="gallery mb-3">
        <button class="btn btn-outline-success" @click="prev">Назад</button>
        <span>{{words[index]}}</span>
        <button class="btn btn-outline-success" @click="next">Вперёд</button>
    </div>
</template>

<style scoped>

</style>

