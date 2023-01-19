<script>
export default {
    name: 'AppTitle',
    data() {
        return {
            message: 'La mia prima app con Vite!'
        }
    }
}
</script>

<template>
    <header class="container mb-5 d-flex align-items-center justify-content-center">
        <h1>{{ message }}</h1>
    </header>
</template>

<style scoped>
header {
    height: 10vh;
    background-color: dodgerblue;
    color: white;
}

h1 {
    text-shadow: 2px 2px black;
}
</style>