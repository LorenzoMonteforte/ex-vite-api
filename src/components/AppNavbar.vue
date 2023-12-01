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
    <button @click="$emit('callFather')">Filtra</button>
</template>

<style scoped>
select {
    height: 30%;
    width: 25%;
    padding: 0 0.5rem;
    border: none;
    border-top-left-radius: 0.5rem;
    border-bottom-left-radius: 0.5rem;
    color: white;
    background-image: url("../assets/img/sfondo.jpg");
}

select>option {
    color: brown;
    background-color: burlywood;
}

button {
    height: 30%;
    padding: 0 0.5rem;
    border: none;
    border-top-right-radius: 0.5rem;
    border-bottom-right-radius: 0.5rem;
    color: white;
    background-image: url("../assets/img/sfondo.jpg");
}

select:focus {
    outline: none;
}
</style>