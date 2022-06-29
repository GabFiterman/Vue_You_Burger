<template>
    <div id="main-burger">
        <h1>Make your burger</h1>
    </div>
</template>

<script>
export default {
    name: 'Banner'
}
</script>

<style scoped>
#main-burger {
    background-image: url('/img/burger.jpg');
    background-position: 0px -45vh;
    background-size: cover;
    height: 75vh;
    display: flex;
    align-items: center;
    justify-content: flex-start;
}

#main-burger h1 {
    color: var(--color-light);
    /* margin-left: 5rem; */
    font-size: 4rem;
    border-radius: 0 4rem 0 0;
    background-color: rgba(255, 255, 255, 0.05);
    border-bottom: solid rgba(255, 255, 255, 0.40) 4px;
    padding: 2rem;
    padding-left: 8rem;
}
</style>