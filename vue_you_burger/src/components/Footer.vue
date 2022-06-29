<template>
    <footer id="footer">
        <p class="">Make your burger &copy; 2022</p>
    </footer>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style scoped>
#footer {
    height: 10vh;
    background-color: var(--color-dark);
    color: var(--color-light);
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    margin-top: 30vh;
}

#footer p {
    font-weight: bold;
}
</style>