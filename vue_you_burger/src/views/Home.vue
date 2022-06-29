<template>
  <main class="main-container" id="home">
    <Banner />
    <h1>Monte o seu burger</h1>
    <BurgerForm />
  </main>
</template>

<script>
import Banner from '../components/Banner.vue';
import BurgerForm from '../components/BurgerForm.vue';

export default {
  name: 'Home',
  components: {
    Banner,
    BurgerForm
  }
}
</script>

<style scoped>
h1 {
  margin-top: 4rem;
}
</style>