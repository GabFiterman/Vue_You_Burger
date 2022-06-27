<template>
    <h1>Bem vindo, {{ nome }}</h1>
    <ul>
        <li>Nome: {{ nome }} {{ sobrenome }}</li>
        <li>Idade: {{ idade }}</li>
        <li>Profissao: {{ profissao }}</li>
    </ul>

    <MultiplosEventos />
    <Reutilizacao />
</template>

<script>
import MultiplosEventos from './MultiplosEventos.vue'
import Reutilizacao from './Reutilizacao.vue'
export default {
    name: 'PrimeiroComponente',
    components: { MultiplosEventos, Reutilizacao },
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