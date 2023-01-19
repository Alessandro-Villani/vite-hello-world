<script>
export default {
    data() {
        return {
            images: ['kumbhakarna.webp', 'neith.webpp', 'ymir.webp']
        }
    },
    methods: {
        getImageUrl(image) {
            return new URL(`../assets/img/${image}`, import.meta.url).href
        }
    }
}
</script>

<template>
    <div class="container">
        <div class="row">
            <div class="col-6 m-auto">
                <img class="img-fluid" :src="getImageUrl(this.images[0])" :alt="this.images[0]">
            </div>
        </div>
    </div>
</template>