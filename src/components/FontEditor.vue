<script>
    export default {
        data() {
            return {
                isBold: false,
                isItalic: false,
                isBackground: false,
                fontSize: 20
            }
        },

        methods: {
           bold() {
            this.isBold = !this.isBold
           },

           italic() {
            this.isItalic = !this.isItalic
           },

           background() {
            this.isBackground = !this.isBackground
           },

           zoomIn() {
            this.fontSize += 5
           },

           zoomOut() {
            this.fontSize -= 5
           }
        }
    }
</script>

<template>
    <div class="font-editor">
        <div class="controls">
            <button  class="btn btn-light btn-bold" @click="bold">B</button>
            <button  class="btn btn-light btn-italic" @click="italic">I</button>
            <button  class="btn btn-light" @click="background">T</button>
            <button  class="btn btn-light btn-plus" @click="zoomIn">+</button>
            <button  class="btn btn-light btn-minus" @click="zoomOut">-</button>
        </div>

        <p
        :class="{
            'bold': isBold,
            'italic': isItalic,
            'background': isBackground,
        }"
        :style="{'font-size': fontSize + `px`}">
            Съешь ещё этих мягких французских булочек
        </p>
    </div>
</template>


<style scoped>
.font-editor .controls {
    display: flex;
    align-items: center;
    gap: 10px;
}
.font-editor p {
    font-size: 20px;
    margin-top: 10px;
}

.bold {
    font-weight: bold;
}

.italic {
    font-style: italic;
}

.background {
    background-color: black;
    color:white;
}
</style>
