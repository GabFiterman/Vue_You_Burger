<template>
    <header id="header">
        <RouterLink to="/">
            <img :src="logo" :alt="alt" id="logo-url" />
        </RouterLink>
        <nav id="nav">
            <RouterLink to="/">Home</RouterLink>
            <RouterLink to="/pedidos">Pedidos</RouterLink>
            <RouterLink to="/Perfil">Perfil</RouterLink>
        </nav>
    </header>
</template>

<script>
export default {
    name: 'Navbar',
    props: ["logo", "alt"]
}
</script>

<style scoped>
#header {
    background-color: var(--color-dark);
    border-bottom: 4px solid #111;
    padding: 15px 50px;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

#logo-url {
    width: 6.5rem;
    transition: var(--transition-default);
}

#logo-url:hover {
    filter: brightness(1.25);
}

#nav a {
    color: var(--color-light);
    text-decoration: none;
    text-transform: uppercase;
    font-size: 1.2rem;
    margin-left: 3rem;
    font-weight: bold;
    transition: var(--transition-default);
}

#nav a:hover {
    color: var(--color-contrast);
}
</style>