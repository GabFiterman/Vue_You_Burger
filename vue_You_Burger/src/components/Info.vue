<template>
    <p>{{ email }}</p>
    <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
    <p v-else>Estou buscando novas oportunidades</p>
    <p>E utilizo as seguintes tecnologias para back-end: </p>
    <ul>
        <li v-for="technology, index in backend_technologies" v-bind:key="index">
            {{ technology }}
        </li>
    </ul>
    <p>E utilizo as seguintes tecnologias para front-end: </p>
    <ul>
        <li v-for="technology in frontend_technologies" v-bind:key="technology.id">
            {{ technology.language }}
        </li>
    </ul>
    <div>
        <button @click="showEmail">{{ texto_botao }}</button>
    </div>

    <p v-show="mostrar_email">Mande uma mensagem para: {{ email }}</p>
    <p>Para acessar meu portfólio basta <a v-bind:href="meu_link" target="_blank">clicar aqui</a></p>
    <Picture />
    <Form />
</template>

<script>
import Picture from './Picture.vue';
import Form from './Form.vue'

export default {
    name: 'Info',
    components: {
        Picture,
        Form
    },
    props: {
        email: String,
        esta_trabalhando: Boolean
    },
    data() {
        return {
            mostrar_email: false,
            meu_link: 'https://github.com/purplewitcher',
            texto_botao: 'Mostrar e-mail',
            backend_technologies: ['JavaScript', 'PHP', 'Python'],
            frontend_technologies: [
                { id: 1, language: 'HTML' },
                { id: 2, language: 'CSS' },
                { id: 3, language: 'VUE' }
            ]
        }
    },
    methods: {
        showEmail() {
            this.mostrar_email = !this.mostrar_email;
            if (!this.mostrar_email)
                this.texto_botao = 'Mostrar e-mail'
            else
                this.texto_botao = 'Esconder e-mail'
        }
    }
}
</script>