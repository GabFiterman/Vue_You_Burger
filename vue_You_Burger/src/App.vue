<template>
  <Header :esta_logado=true />
  <PrimeiroComponente />
  <LifeCycle />
  <Pessoa />
</template>

<script>
import PrimeiroComponente from './components/PrimeiroComponente.vue';
import LifeCycle from './components/LifeCycle.vue';
import Pessoa from './components/Pessoa.vue';
import Header from './components/Header.vue';

export default {
  name: 'App',
  components: {
    PrimeiroComponente,
    LifeCycle,
    Pessoa,
    Header
  }
}
</script>

<style>
body {
  background-color: rgb(50, 50, 50);
  color: white;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

a {
  color: rgb(147, 217, 218)
}
</style>