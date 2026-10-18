
<script>
export default {
    data() {
        return {
            img: "src/assets/mem-generator/meme-default.png",
            topText: "it doesnt work, why?",
            bottomText: "it works, why?"
        }
    }
}

</script>


<template>
    <div class="mem-gen">
        <div class="meme">
            <p class="top-text">
                {{topText}}
            </p>
            <p class="bottom-text">
                {{bottomText}}
            </p>
            <img :src="img">
        </div>
        
        <hr>
        
        <div class="input-group mb-3">
            <span class="input-group-text">Верхняя надпись</span>
            <textarea class="form-control" v-model="topText"></textarea>
        </div>

        <div class="input-group mb-3">
            <span class="input-group-text">Нижняя надпись</span>
            <textarea class="form-control" v-model="bottomText"></textarea>
        </div>


        <div class="input-group mb-3">
            <span class="input-group-text">Изображение</span>
            <textarea  class="form-control" v-model="img"></textarea>
        </div>
    </div>
</template>

<style scoped>

.mem-gen img {
    max-width: 500px;
    width: 100%;
    height: auto;
}

.mem-gen .meme {
    position: relative;
    text-align: center;
}

.mem-gen span {
    width: 150px;
}

.top-text,
.bottom-text {
    position: absolute;
    width: 100%;
    text-align: center;
    color: #ffffff;
    font-family: 'Arial', sans-serif;
    font-size: 30px;
    font-weight: 700;
    margin: 0;
    text-shadow:
        0 -2px 0 #000000,
        0 2px 0 #000000,
        -2px -0 0 #000000,
        2px -0 0 #000000,
        -2px 0 0 #000000,
        2px 0 0 #000000,
        -1px -2px 0 #000000,
        1px -2px 0 #000000,
        -1px 2px 0 #000000,
        1px 2px 0 #000000,
        -2px -1px 0 #000000,
        2px -1px 0 #000000,
        -2px 1px 0 #000000,
        2px 1px 0 #000000,
        -2px -2px 0 #000000,
        2px -2px 0 #000000,
        -2px 2px 0 #000000,
        2px 2px 0 #000000;
}

.top-text {
    top: 20px;
}

.bottom-text {
    bottom: 20px;
}

hr {
    margin: 40px auto;
    width: 50%;
    height: 8px;
    background-color: #41b883;
    border: 0;
    border-top: 3px solid #35495e;
}
</style>