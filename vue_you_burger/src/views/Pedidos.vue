<template>
  <main class="main-container" id="pedidos">
    <h1>Gerenciar pedidos: </h1>
    <Dashboard />
  </main>
</template>

<script>
import Dashboard from "../components/Dashboard.vue";

export default{
    name: "Pedidos",
    components: { Dashboard }
}
</script>

<style scoped>
</style>