<script>
import AppHeader from "./components/AppHeader.vue";
import Card from "./components/Card.vue";
import axios, { isCancel, AxiosError } from 'axios';
import { store } from "./store";
export default {
    components: {
        AppHeader,
        Card
    },
    data() {
        return {
            birrifici: [],
            store
        }
    },
    methods: {
        downloadAPI: function () {
            this.birrifici = [];
            let url;
            if (this.store.inputUser == "") {
                url = "https://api.openbrewerydb.org/v1/breweries?by_country=ireland&per_page=10";
            } else {
                url = "https://api.openbrewerydb.org/v1/breweries?by_country=ireland&per_page=10&by_type=" + this.store.inputUser;
            }
            axios.get(url)
                .then(response => {
                    for (let i = 0; i < response.data.length; i++) {
                        this.birrifici.push({
                            name: response.data[i].name,
                            brewery_type: response.data[i].brewery_type,
                            city: response.data[i].city,
                            state_province: response.data[i].state_province,
                            country: response.data[i].country,
                            phone: response.data[i].phone,
                            website_url: response.data[i].website_url,
                            street: response.data[i].street
                        })
                    }
                })
        }
    },
    mounted() {
        this.downloadAPI();
    }
}
</script>

<template>
    <AppHeader @callFather="downloadAPI()" />
    <Card v-for="birrificio in birrifici" :name="birrificio.name" :brewery_type="birrificio.brewery_type"
        :city="birrificio.city" :state_province="birrificio.state_province" :country="birrificio.country"
        :phone="birrificio.phone" :website_url="birrificio.website_url" :street="birrificio.street" />
</template>

<style scoped></style>
