<template>
    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Projetos</a></li>
        <li><a href="#">Contato</a></li>
        <li v-if="esta_logado"><a href="#">Meu perfil</a></li>
    </ul>
</template>

<script>
export default {
    name: 'Header',
    props: ["esta_logado"]
}
</script>

<style scoped>
ul {
    background-color: rgb(95, 95, 95);
    padding: 2rem;
}

li {
    display: inline;
    margin-left: 4rem;
    font-size: 1.2rem;
}

a {
    text-decoration: none
}

a:hover {
    filter: brightness(0.75);
}
</style>