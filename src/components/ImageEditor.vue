<script>
export default {
    data() {
        return {
            width: 200,
            image: `src/assets/image-editor/sun.png`,
            rotation: 0,
            index: 0,
            colors: [`white`, `violet`, `pink`, `lightblue`, `lightgreen`, `yellow`]
        }

    },

    methods: {
        zoomIn() {
            this.width += 5
        },

        zoomOut() {
            this.width -= 5
        },

        left() {
            this.rotation -= 5
        },

        right() {
            this.rotation += 5
        },

        newBack() {
            if (this.index > this.colors.length - 1) {
                this.index = 0
            } else { 
                this.index++
            }
            
        }
    }
}
</script>

<template>
    <div class="image-editor" :style="{'background-color': colors[index]}">
        <button class="btn btn-outline-warning less" @click="zoomOut">-</button>
        <button class="btn btn-outline-warning more" @click="zoomIn">+</button>

        <img :src="image" :style="{
            'width': width + `px`, 
            'rotate': rotation + `deg`}" 
            @click="newBack">

        <button @click="left" class="btn btn-outline-warning left">Налево</button>
        <button @click="right" class="btn btn-outline-warning right">Направо</button>
    </div>
</template>


<style scoped>
.image-editor {
    height: 300px;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
    border: 1px dotted black;
    user-select: none;
}

.less {
    position: absolute;
    top: 0;
    left: 0;
}

.more {
    position: absolute;
    top: 0;
    right: 0;
}

.left {
    position: absolute;
    bottom: 0;
    left: 0;
}

.right {
    position: absolute;
    bottom: 0;
    right: 0;
}
</style>
