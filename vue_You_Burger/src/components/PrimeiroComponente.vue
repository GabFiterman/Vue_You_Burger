<template>
    <h1>Bem vindo, {{ nome }}</h1>
    <ul>
        <li>Nome: {{ nome }} {{ sobrenome }}</li>
        <li>Idade: {{ idade }}</li>
        <li>Profissao: {{ profissao }}</li>
    </ul>
</template>

<script>
export default {
    name: 'PrimeiroComponente',
    data() {
        return {
            nome: 'Gabriel',
            sobrenome: 'Fiterman',
            idade: 23,
            profissao: 'Desenvolvedor'
        }
    }
}
</script>