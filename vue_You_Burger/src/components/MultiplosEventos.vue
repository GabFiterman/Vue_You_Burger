<template>
    <div class="multiplosEventos">
        <h1>Múltiplos eventos</h1>
        <button @click="primeiro(txt1, $event), segundo(txt2, $event)">Ativar
            Múltiplos Eventos</button>
        <p>{{ multiplos_eventos }}</p>
    </div>
</template>

<script>
export default {
    name: 'MultiplosEventos',
    data() {
        return {
            multiplos_eventos: '',
            txt1: 'Primeiro evento ativado!',
            txt2: 'Segundo evento ativado!'
        }
    },
    methods: {
        primeiro(txt, e) {
            this.multiplos_eventos = txt
        },
        segundo(txt, e) {
            setTimeout(() => this.multiplos_eventos = txt, 500)
        }
    }
}
</script>

<style scoped>
.multiplosEventos {
    background-color: black;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 5rem;
}

h1 {
    color: red;
}

button {
    font-size: 1.2rem;
    padding: 1rem 2rem;
    border: none;
    border-radius: 2rem;
    cursor: pointer;
}
</style>