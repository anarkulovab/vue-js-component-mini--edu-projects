<script>
export default {
    props: {
        book: Object,
        count: Number
    },

    data() {
        return {
            countData: 0
        }
    },
    computed: {
        authorUpperCase() {
            return this.book.author.toUpperCase()
        }
    }


}
</script>
<template>
    <div class="card">
        <!-- Счетчик из Дата: {{ countData }} <br>
        Счетчик из Пропс: {{ count }} -->
        <img :src="'src/assets/books-app/' + book.image + '.png'" class="card-img-top" alt="..." @click="countData++">
        <div class="card-body">
            <p class="card-subtitle text-secondary">{{ authorUpperCase }}</p>
            <h5 class="card-title">{{ book.title }}</h5>
            <p class="card-subtitle text-warning rating mt-auto"><span>{{ book.rating }}</span>
                <img :src="'src/assets/books-app/star.png'" class="star">
            </p>
        </div>
    </div>
</template>
<style scoped>
.star {
    width: 16px;
    height: 16px;
}

.rating {
    display: flex;
    align-items: center;
    gap: 2px;
}

.card-body {
    display: flex;
    min-height: 130px;
    flex-direction: column;
}
</style>