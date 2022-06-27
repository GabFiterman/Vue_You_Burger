<template>
    <button @click="ativar">Clique aqui!</button>
    <span v-show="ativou">Ativado!</span>
</template>

<script>
export default {
    name: 'Reutilizacao',
    data() {
        return {
            ativou: false
        }
    },
    methods: {
        ativar() {
            this.ativou = !this.ativou;
            console.log('O método ativar foi ATIVADO');
        }
    }
}
</script>