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
    display: flex;
    align-items: center;
    justify-content: center;
    background-image: url("../assets/img/sfondoHeader.jpg");
}
</style>