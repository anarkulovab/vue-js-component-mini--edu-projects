<script>
export default {
    data() {
        return {
            images: [`src/assets/image-gallery/1.png`, `src/assets/image-gallery/2.png`, `src/assets/image-gallery/3.png`],
            index: 0
        }
    },

    methods: {
        next() {
            if (this.index == this.images.length - 1) {
                this.index = 0;
            } else {
                this.index++;
            }
        },

        prev() {
            if (this.index == 0) {
                this.index = this.images.length - 1;
            } else {
                this.index--;
            }
        }
    }
}
</script>

<template>
    <button class="btn btn-outline-danger" @click="prev">Назад</button>
    <img class="bb" :src="images[index]" alt="">
    <button class="btn btn-outline-danger" @click="next">Вперед</button>
</template>

<style scoped>
.bb{
    width: 250px;
    height: 300px;
}
</style>

