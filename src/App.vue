<script>
import Card from "./components/Card.vue";
import axios, { isCancel, AxiosError } from 'axios';
export default {
    components: {
        Card
    },
    data() {
        return {
            birrifici: []
        }
    },
    methods: {
        downloadAPI: function () {
            axios.get("https://api.openbrewerydb.org/v1/breweries?by_country=ireland&per_page=10")
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
    <Card v-for="birrificio in birrifici" :name="birrificio.name" :brewery_type="birrificio.brewery_type"
        :city="birrificio.city" :state_province="birrificio.state_province" :country="birrificio.country"
        :phone="birrificio.phone" :website_url="birrificio.website_url" :street="birrificio.street" />
</template>

<style scoped></style>
