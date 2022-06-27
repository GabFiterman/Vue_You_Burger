<template>
    <h2>Esta é a descrição da pessoa: {{ nome }}</h2>
    <Info :email="email" :esta_trabalhando=true />
</template>

<script>
import Info from './Info.vue'
export default {
    name: 'Pessoa',
    components: {
        Info
    },
    data() {
        return {
            nome: 'Gabriel',
            email: 'gabrielfiterman@lett.digital'
        }
    }
}
</script>