Добавь data-свойство isDark, которая будет отвечать за тёмный фон
Добавь data-свойство lamp, которая будет отвечать за путь изображения
Добавь метод toggle, который будет менять isDark и lamp на противоположные
<script>
    export default {
        data() {
            return {
                isDark: false,
                lamp: [`src/assets/lamp/light.png`, `src/assets/lamp/dark.png`],
                index: 0
            }
            
        },

        methods: {
            toggle() {
                this.isDark = !this.isDark;
                if (this.index == 0) {
                    this.index = 1
                } else (this.index = 0)
            }
        }
    }
</script>

<template>
    <div class="lamp-toggle" :class="{'dark': isDark}">
        <img :src="lamp[index]" @click="toggle">
    </div>
</template>


<style scoped>
.lamp-toggle {
    transition: background-color 500ms;
}

.lamp-toggle img {
    width: 200px;
    height: 200px;
}
.lamp-toggle.dark {
    background-color: black;
}
</style>

