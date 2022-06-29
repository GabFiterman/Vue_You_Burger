<template>
  <Navbar :logo="logo_src" :alt="app_name" />
  <RouterView />
  <Footer />
</template>

<script>
// import { RouterLink, RouterView } from 'vue-router'
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';

export default {
  components: {
    Navbar,
    Footer
  },
  data() {
    return {
      logo_src: '/img/logo.png',
      app_name: 'Make your burger'
    }
  }
}

</script>

<style>
:root {
  --transition-default: all 0.65s;

  --color-dark: #222222;
  --color-light: #ccc;
  --color-contrast: #EFA335;

}

body {
  font-family: 'Poppins', 'Helvetica', 'Arial', sans-serif;
}

.main-container {
  min-height: 25vh;
}

h1 {
  text-align: center;
  font-size: 42px;
  margin-bottom: 2rem;
  font-weight: bold;
}

b{
  font-weight: bold;
}
</style>
