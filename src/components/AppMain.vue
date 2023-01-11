<script>
import axios from 'axios';

import { store } from '../store.js';
import ElementCard from './ElementCard.vue';

export default {
    name: 'AppMain',

    components: {
        ElementCard
    },

    data() {
        return {
            store,
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0'
        }
    },

    methods: {
        getCards() {
            axios.get(this.apiUrl, {
                params: {

                }
            })
                .then((response) => {
                    console.log(response.data.data);
                    this.store.cardsList = response.data.data;
                })
                .catch(function (error) {
                    console.log(error);
                })
        }
    },

    created() {
        this.getCards()
    },
}
</script>

<template>
    <div class="container">
        <ElementCard v-for="cardEl in store.cardsList" :card="cardEl" />
    </div>
</template>

<style lang="scss" scoped>

</style>