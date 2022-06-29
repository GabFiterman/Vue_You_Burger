<template>
    <section>

        <form id="burger-form" @submit="createBurger">

            <div class="input-container">
                <label for="nome">Nome do cliente:</label>
                <input type="text" id="nome" name="name" v-model="nome" placeholder="Digite o seu nome" />
            </div>

            <div class="input-container">
                <label for="pao">Escolha o pão:</label>
                <select name="pao" id="pao" v-model="pao">
                    <option value="">Selecione o pão</option>
                    <option v-for="pao in paes" :key="pao.id" :value="pao.tipo">{{ pao.tipo }}</option>
                </select>
            </div>

            <div class="input-container">
                <label for="queijo">Escolha o queijo: </label>
                <select name="queijo" id="queijo" v-model="queijo">
                    <option value="">Selecione o queijo</option>
                    <option v-for="queijo in queijos" :key="queijo.id" :value="queijo.tipo">{{ queijo.tipo }}</option>
                </select>
            </div>

            <div class="input-container">
                <label for="carne">Escolha sua carne:</label>
                <select name="carne" id="carne" v-model="carne">
                    <option value="">Selecione a carne</option>
                    <option v-for="carne in carnes" :key="carne.id" :value="carne.tipo">{{ carne.tipo }}</option>
                </select>
            </div>

            <div id="opcionais-container" class="input-container">
                <label id="opcionais-title" for="Opcionais">Selecione os opcionais:</label>
                <div class="checkbox-container" v-for="opcional in opcionaisData" :key="opcional.id">
                    <input type="checkbox" name="opcionais" v-model="opcionais" :value="opcional.tipo" />
                    <span>{{ opcional.tipo }}</span>
                </div>
            </div>

            <div class="input-container">
                <input type="submit" class="submit-btn" value="Criar meu burger!" />
            </div>
        </form>
        <Message v-show="msg" :msg="msg" :nome="pedidoNome" />

    </section>
</template>

<script>
import Message from "./Message.vue";

export default {
    name: "BurgerForm",
    data() {
        return {
            nome: null,
            paes: null,
            queijos: null,
            carnes: null,
            opcionaisData: null,
            pao: null,
            queijo: null,
            carne: null,
            opcionais: [],
            msg: null,
            pedido: null,
            pedidoNome: null
        }
    },
    methods: {
        async getIngredientes() {
            const req = await fetch("http://localhost:3000/ingredientes");

            const data = await req.json();

            this.paes = data.paes;
            this.queijos = data.queijos;
            this.carnes = data.carnes;
            this.opcionaisData = data.opcionais;
        },
        //--------------------------------------------------------
        async createBurger(e) {

            e.preventDefault();

            const data = {
                nome: this.nome,
                pao: this.pao,
                queijo: this.queijo,
                carne: this.carne,
                opcionais: Array.from(this.opcionais),
                status: "Solicitado"
            };

            const dataJson = JSON.stringify(data);

            const req = await fetch("http://localhost:3000/burgers", {
                method: "POST",
                headers: {
                    "Content-Type": "application/json"
                },
                body: dataJson
            });

            const res = await req.json();

            this.msg = `Seu pedido Nº ${res.id} foi solicitado com sucesso`;
            this.pedidoNome = this.nome;
            setTimeout(() => this.msg = "", 8000);

            this.nome = "";
            this.paes = "";
            this.queijos = "";
            this.carnes = "";
            this.opcionais = [];
        }
    },
    mounted() {
        this.getIngredientes();
    },
    components: {
        Message
    }
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