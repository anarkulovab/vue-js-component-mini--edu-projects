<script>
export default {
	data() {
		return {
			images: ['src/assets/image-gallery-array/angry.png', 'src/assets/image-gallery-array/sleep.png', 'src/assets/image-gallery-array/study.png'],

			imagesObj: [{image: 'src/assets/image-gallery-array/angry.png', count: 0}, 
					{image: 'src/assets/image-gallery-array/sleep.png', count: 0}, 
					{image: 'src/assets/image-gallery-array/study.png', count: 0}],

			selectedImage: ``
		};
	},

	methods: {
		closeUp(item) {
			this.selectedImage = item;
		}

	},
};
</script>

<template>
	<div class="image-gallery">
		<div class="image-item" v-for="(item, index) in images" @click="closeUp(index)" :class="{'selected': selectedImage == index}">
			<img :src="item"/>
		</div>
	</div>
	<br>
	<div class="image-gallery">
		<div class="image-item" v-for="(item, index) in imagesObj" @click="closeUp(index)" :class="{'selected': selectedImage == index}">
			<img :src="item.image" @click="item.count++"/>
			<p>{{ item.count }}</p>
		</div>
	</div>
</template>

<style scoped>
.image-gallery {
	display: flex;
	flex-wrap: wrap;
	gap: 40px;
}

.image-item {
	width: 100px;
	transition: scale 500ms;
}

.image-item img {
	width: 100%;
}

.selected {
	scale: 1.8;
}

.current-image {
    width: 300px;
}
</style>
