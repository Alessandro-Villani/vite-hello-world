<script>
export default {
    props: ['url', 'name', 'description']
}
</script>

<template>
    <section class="description">
        <div class="description-header text-center">
            <h2>{{ name }}</h2>
        </div>
        <div class="description-body">
            <img class="float-start image-fluid me-3" :src="url" :alt="name">
            <p>{{ description }}</p>
        </div>
    </section>
</template>

<style scoped>
img {
    width: 300px;
}
</style>