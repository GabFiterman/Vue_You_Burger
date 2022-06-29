<template>
    <section>
        <p>Componente de mensagem</p>
        <form id="burger-form">

            <div class="input-container">
                <label for="nome">Nome do cliente:</label>
                <input type="text" id="nome" name="name" v-model="nome" placeholder="Digite o seu nome" />
            </div>

            <div class="input-container">
                <label for="pao">Escolha o pão:</label>
                <select name="pao" id="pao" v-model="pao">
                    <option value="">Selecione o pão</option>
                    <option value="integral">Integral</option>
                </select>
            </div>

            <div class="input-container">
                <label for="carne">Escolha sua carne:</label>
                <select name="carne" id="carne" v-model="carne">
                    <option value="">Selecione a carne</option>
                    <option value="picanha">Picanha</option>
                </select>
            </div>

            <div id="opcionais-container" class="input-container">
                <label id="opcionais-title" for="Opcionais">Selecione os opcionais:</label>
                <div class="checkbox-container">
                    <input type="checkbox" name="opcionais" v-model="opcionais" value="salame" />
                    <span>Salame</span>
                </div>

                <div class="checkbox-container">
                    <input type="checkbox" name="opcionais" v-model="opcionais" value="salame" />
                    <span>Salame</span>
                </div>

                <div class="checkbox-container">
                    <input type="checkbox" name="opcionais" v-model="opcionais" value="salame" />
                    <span>Salame</span>
                </div>
            </div>

            <div class="input-container">
                <input type="submit" class="submit-btn" value="Criar meu burger!" />
            </div>
        </form>
    </section>
</template>

<script>
export default {
    name: 'BurgerForm'
}
</script>

<style scoped>
#burger-form {
    width: 25vw;
    margin: 0 auto;

}

.input-container {
    display: flex;
    flex-direction: column;
    margin-bottom: 2rem;
}

label {
    font-weight: bold;
    margin-bottom: 1.2rem;
    color: #222;
    padding: 0.6rem 0.9rem;
    border-left: 4px solid var(--color-contrast);
}

input,
select {
    padding: 0.6rem 0.9rem;
    width: 20vw;
}

#opcionais-container {
    flex-direction: row;
    flex-wrap: wrap;
}

.checkbox-container {
    display: flex;
    align-items: flex-start;
    width: 50%;
    margin-bottom: 20px;
}

#opcionais-title {
    width: 100%;
}

.checkbox-container span,
.checkbox-container input {
    width: auto;
}

.checkbox-container input {
    margin-left: 6px;
    font-weight: bold;
}

.submit-btn {
    background-color: var(--color-dark);
    color: var(--color-contrast);
    font-size: 1.1rem;
    font-weight: bold;
    border: none;
    border-radius: 0.5rem;
    transition: var(--transition-default);
    padding: 1rem 1.3rem;
}

.submit-btn:hover {
    cursor: pointer;
    filter: brightness(1.5);
    font-size: 1.15rem;
}
</style>