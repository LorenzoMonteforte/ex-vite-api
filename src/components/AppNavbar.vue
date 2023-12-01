<script>
import { store } from "../store";
export default {
    name: "AppNavbar",
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <select v-model="this.store.inputUser">
        <option value="">Mostra tutti i risultati</option>
        <option value="micro">Micro</option>
        <option value="nano">Nano</option>
        <option value="regional">Regional</option>
        <option value="brewpub">Brewpub</option>
        <option value="large">Large</option>
        <option value="planning">Planning</option>
        <option value="bar">Bar</option>
        <option value="contract">Contract</option>
        <option value="proprietor">Proprietor</option>
        <option value="closed">Closed</option>
    </select>
    <button @click="$emit('callFather')">Cliccami</button>
</template>

<style scoped></style>