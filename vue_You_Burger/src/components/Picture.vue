<template>
    <img :src="avatar" :alt="descricao" />
    <MudarImagem @mudar-imagem="mudarImagem" />
</template>

<script>
import MudarImagem from './MudarImagem.vue'
export default {
    name: 'Picture',
    components: {
        MudarImagem
    },
    data() {
        return {
            avatar: '/img/avatar.png',
            descricao: 'Foto Gabriel Fiterman'
        }
    },
    methods: {
        mudarImagem() {
            if (this.avatar === '/img/avatar.png') {
                this.avatar = '/img/avatar_2.png';
            } else {
                this.avatar = '/img/avatar.png';
            }
        }
    }
}
</script>

<style scoped>
img {
    width: 150px;
}
</style>