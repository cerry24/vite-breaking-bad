<script>
import { store } from '../store.js';
import axios from 'axios';

export default {
    name: 'AppMain',

    data() {
        return {
            store,
            apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0'
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
    <div>

    </div>
</template>

<style lang="scss">

</style>