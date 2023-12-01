<script>
import AppNavbar from "./AppNavbar.vue";
export default {
    name: "AppHeader",
    components: {
        AppNavbar
    }
}
</script>

<template>
    <header>
        <AppNavbar @callFather="$emit('callFather')" />
    </header>
</template>

<style scoped>
header {
    height: 100px;
    background-color: red;
}
</style>