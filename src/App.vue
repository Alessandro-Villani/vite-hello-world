
<script>
import AppHero from './components/AppHero.vue';
import AppTitle from './components/AppTitle.vue';

export default {
  data() {
    return {

    }
  },
  components: {
    AppTitle,
    AppHero
  }
}

</script>

<template>
  <AppTitle />
  <main class="container py-5">
    <AppHero />
  </main>
  <footer class="container">

  </footer>
</template>

<style>
main {
  background-color: rgb(47, 49, 54);
  height: 80vh;
}

footer {
  height: 10vh;
  background-color: dodgerblue;
}
</style>