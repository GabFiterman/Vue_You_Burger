<template>
    <div class="message-container">
        <h2 v-show="nome"><b>{{ nome }}</b>, obrigado pelo pedido</h2>
        <p>{{ msg }}</p>
    </div>
</template>

<script>
export default {
    name: "Message",
    props: {
        nome: String,
        msg: String
    }
}
</script>

<style scoped>
.message-container {
    color: #004085;
    background-color: #CCE5FF;
    border: 2px solid #B8DAFF;
    border-radius: 5px;
    padding: 10px;
    max-width: 400px;
    margin: 30px auto;
}

.message-container h2 {
    font-size: 1.3rem;
}
</style>