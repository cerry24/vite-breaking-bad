<script>
import { store } from '../store.js';

import ElementCard from './ElementCard.vue';

export default {
    name: 'AppMain',

    components: {
        ElementCard
    },

    data() {
        return {
            store
        }
    },
}
</script>

<template>
    <div class="container">
        <ElementCard v-for="cardEl in store.cardsList" :card="cardEl" />
    </div>
</template>