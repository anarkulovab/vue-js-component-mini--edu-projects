<script>
export default {
    data() {
        return {
            // текст
            title: 'Text',

            // цвет текста
            fontColor: '#52ff66',
            // цвет фона текста
            bgColor: '#000000',
            // размер текста
            fontSize: 50,
            // шрифт
            font: 'Times New Roman',
            // caps
            capsOn: false,
            isVisible: true
        }
    }
}
</script>

<template>
    <div class="logo-editor">

        <div class="card">

            <div class="card-body">
                <input v-model="isVisible" class="form-check-input" type="checkbox" id="checkDefault">
                <label class="form-check-label" for="checkDefault">Показывать настройки</label>
                <input v-model="title" class="form-control mt-3 text-center">
                <input v-if="isVisible" v-model="fontSize" + `px` type="range" class="form-control mt-3" min="20"
                    max="100">
                <div class="d-flex" v-if="isVisible">
                    <input v-model="fontColor" type="color" class="form-control mt-3">
                    <input v-model="bgColor" type="color" class="form-control mt-3">
                </div>

                <select v-if="isVisible" class="form-select" v-model="font" aria-label="Default select example">
                    <option>Courier New</option>
                    <option>Times New Roman</option>
                    <option>Arial</option>
                </select>

                <input v-if="isVisible" v-model="capsOn" class="form-check-input" type="checkbox" value=""
                    id="checkDefault">
                <label class="form-check-label" for="checkDefault">Капслок</label>

            </div>
        </div>


        <div class="result-container">
            <p class="result"
                :style="{ 'color': fontColor, 'background-color': bgColor, 'font-size': fontSize + `px`, 'font-family': font }"
                :class="{ 'capsOn': capsOn }">
                <span>
                    {{ title }}
                </span>
            </p>
        </div>

    </div>
</template>


<style scoped>
.logo-editor {
    max-width: 1300px;
    margin: 0 auto;
}

.logo-editor .card {
    width: 100%;
}

.logo-editor .result {
    display: flex;
    align-items: center;
    justify-content: center;
}

.capsOn {
    text-transform: uppercase;
}
</style>