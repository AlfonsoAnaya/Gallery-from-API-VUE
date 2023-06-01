<script setup lang="ts">
</script>

<template>
    <footer>
        <p>Website by: <a href="https://alfonsoanaya.netlify.app/"> Alfonso Anaya</a></p>
    </footer>

</template>

<style scoped>
footer {
    width: 100%;
    font-family: var(--font-secondary);
    font-size: .9em;
    text-align: center;
    height: 3em;
    background-color: var(--color-primary);
    display: flex;
    justify-content: center;
    align-items: center;
}

a {
    text-decoration: underline dotted;
    cursor: pointer;
    color: var(--color-font-dark);
}

a:hover {
    text-decoration: underline solid;
    color: var(--color-btn);
    cursor: pointer;
    color: rgb(0, 118, 227);
}
</style>