<template>
    <button @click="$emit('mudarImagem')">Trocar imagem de perfil</button>
</template>

<script>
export default {
    name: 'MudarImagem',
    emits: ['mudarimagem']
}
</script>