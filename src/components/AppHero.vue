<script>
import AppHeroDescription from './AppHeroDescription.vue';

export default {
    data() {
        return {
            images: [
                {
                    url: "kumbhakarna.webp",
                    url2: "KumbhakarnaCard.webp",
                    name: "Khumbakarna",
                    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam assumenda ipsum eius nesciunt sint itaque accusamus, architecto voluptate at officia exercitationem eligendi alias suscipit sunt placeat neque fuga. Officia, illum."
                },
                {
                    url: "neith.webp",
                    url2: "NeithCard.webp",
                    name: "Neith",
                    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam assumenda ipsum eius nesciunt sint itaque accusamus, architecto voluptate at officia exercitationem eligendi alias suscipit sunt placeat neque fuga. Officia, illum."
                },
                {
                    url: "ymir.webp",
                    url2: "YmirCard.webp",
                    name: "Ymir",
                    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam assumenda ipsum eius nesciunt sint itaque accusamus, architecto voluptate at officia exercitationem eligendi alias suscipit sunt placeat neque fuga. Officia, illum."
                }
            ],
            currentIndex: 0,
            interval: undefined,
            descriptionShow: false
        };
    },
    methods: {
        getImageUrl(image) {
            return new URL(`../assets/img/${image}`, import.meta.url).href;
        },
        slideImage() {
            this.interval = setInterval(() => {
                this.currentIndex = this.currentIndex === this.images.length - 1 ? 0 : ++this.currentIndex;
            }, 2000);
        },
        toggleDescription() {
            clearInterval(this.interval);
            this.descriptionShow = !this.descriptionShow;
            if (!this.descriptionShow) {
                this.slideImage()
            }
        }
    },
    mounted() {
        this.slideImage();
    },
    components: { AppHeroDescription }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="slider col-6 m-auto d-flex justify-content-center mb-3" @click="toggleDescription()">
                <img class="img-fluid" :src="getImageUrl(this.images[this.currentIndex].url)"
                    :alt="this.images[this.currentIndex].name">
                <h3>{{ this.images[this.currentIndex].name }}</h3>
            </div>
        </div>
        <div class="row">
            <div class="col-6 m-auto">
                <AppHeroDescription v-if="descriptionShow" :url="getImageUrl(this.images[this.currentIndex].url2)"
                    :name="this.images[this.currentIndex].name"
                    :description="this.images[this.currentIndex].description" />
            </div>
        </div>
    </div>
</template>

<style scoped>
.slider {
    position: relative;
    cursor: pointer;
    transition: all 0.5s;
}

.slider:hover {
    scale: 1.1;
}

h3 {
    position: absolute;
    bottom: 0;
    color: white;
    text-shadow: 2px 2px black;
}
</style>