<script>
    export default {
        data() {
            return {
                images: [`src/assets/password/show.png`, `src/assets/password/hide.png`],
                type: [`password`, `text`],
                index: 0
            }
        },

        methods: {
            toggle() {
                if (this.index == 0){
                    this.index ++
                } else (this.index --)
            }
        }
    }
</script>

<template>
    <div class="password-input mb-3">
        <div class="input-group mb-3">          
            <input :type="type[index]" value="1234" class="form-control" >
            <button class="btn btn-outline-secondary" @click="toggle">
                <img :src="images[index]">
            </button>
        </div>
    </div>
</template>


<style scoped>
.password-input img {
    height: 24px;
}



</style>
