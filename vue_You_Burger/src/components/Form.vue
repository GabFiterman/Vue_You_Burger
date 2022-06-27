<template>
    <h2>Meu formulário</h2>
    <form action="" @submit="enviarFormulario($event)">
        <div>
            <input type="text" v-model="name">
        </div>
        <div>
            <input type="text" v-model="email">
        </div>
        <div>
            <Submit />
        </div>
    </form>
</template>

<script>
import InputText from './Form/InputText.vue';
import Submit from './Form/Submit.vue';
export default {
    name: 'Form',
    components: { InputText, Submit },
    data() {
        return {
            name: '',
            email: ''
        }
    },
    methods: {
        enviarFormulario(e) {
            const name = this.name;
            const email = this.email;

            e.preventDefault();
            console.log('Enviar Formulário!');
            console.log('O nome é: ' + name);
            console.log('O email é: ' + email)
        }
    }
}
</script>

<style>
input {
    background-color: rgb(94, 94, 94);
    color: #fff;
    padding: 0.5rem 1.5rem;
    border: none;
    border-radius: 2rem;
    margin-bottom: 2rem;
    min-width: 25rem;
    font-size: 1.4rem;
}
</style>